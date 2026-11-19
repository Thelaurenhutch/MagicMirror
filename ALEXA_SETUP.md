# 🗣️ Alexa Integration Setup Guide

## How It Works

Your MagicMirror will display your Todoist "Grocery List" and Alexa can add to it!

```
You say: "Alexa, add milk"
         ↓
   Goes to Todoist
         ↓
   Shows on Mirror
```

## Prerequisites

✅ You have:
- Alexa device (Echo, Echo Dot, etc)
- Todoist account with "Grocery List" project
- Both set up per the TODOIST_SETUP.md guide

## Step-by-Step Setup

### 1. Enable Todoist Skill in Alexa App

**On your phone:**
1. Open **Alexa app** (download if needed)
2. Bottom right → **More** (three dots)
3. Select **Skills & Games**
4. Search: **"Todoist"**
5. Tap the **Todoist** result (official one, by Todoist Inc)
6. Click **Enable**
7. Click **Continue to Todoist**
8. **Sign in** with your Todoist email/password
9. You'll see permission request - **Allow**
10. Select which projects: Check **"Grocery List"** ✅
11. Click **Allow**
12. Done! You should see "Successfully linked"

### 2. Test It

**Say to Alexa:**
```
"Alexa, add milk to Grocery List"
```

**Expected result:**
- Alexa confirms: "Added milk to Grocery List"
- Item appears in Todoist app within seconds
- Item appears on your mirror within 1-2 minutes

### 3. Voice Commands Examples

```
"Alexa, add eggs to Grocery List"
"Alexa, add chicken to Todoist"
"Alexa, what's on my Grocery List?"
"Alexa, check off milk in Grocery List"
"Alexa, add butter and bread to Grocery List"  (multiple items)
```

## 📱 Your Partner's Setup

If your partner also has an Alexa device and wants to add items:

1. Install **Todoist skill** on their Alexa device (steps 1-12 above)
2. They sign in with **YOUR shared Todoist account** (the one with Grocery List)
3. That's it! They can now say:
   - "Alexa, add cheese to Grocery List"
   - Items appear on mirror automatically

## 🪞 What Shows on Your Mirror

**Bottom left corner:**
```
📋 Grocery List
├─ Milk
├─ Eggs  
├─ Bread
└─ Butter
```

As items are checked off in Todoist or via Alexa, they fade out.

## ⚙️ Advanced: Multiple Projects

Want to track multiple lists (Groceries, Household, Todo)?

**Setup in Todoist:**
1. Create projects: "Groceries", "Household", "Todo"
2. Share them with your partner
3. Enable Todoist skill to access all projects

**In your Mirror config (config/config.js):**
```javascript
{
  module: "MMM-Todoist",
  position: "bottom_left",
  config: {
    accessToken: "YOUR_TODOIST_API_TOKEN",
    projects: ["Groceries", "Household", "Todo"],
    displayLastSyncTime: false,
    maxWidth: "400px"
  }
}
```

Then use:
- "Alexa, add milk to Groceries"
- "Alexa, add sponges to Household"
- "Alexa, add call mom to Todo"

## 🆘 Troubleshooting

### "Skill is not responding"
- Check internet connection on both Alexa and Mirror
- Try disabling and re-enabling the skill
- Restart Alexa device

### Items not showing on Mirror
- Wait 1-2 minutes (Todoist syncs to mirror every 2 mins)
- Verify API token is correct in config.js
- Restart MagicMirror
- Check project name matches exactly

### Alexa can't find the skill
- Search for "Todoist" (not "Todo" or "Task")
- Make sure you're using official Todoist skill
- Try again, there may be slight delays in Alexa's skill discovery

### Partner's Alexa not adding items
- Both must use same Todoist account
- Both must enable the same Todoist skill
- Verify project name is spelled identically

## 💡 Pro Tips

1. **Voice feedback:** Alexa will confirm each item added
2. **Faster shopping:** Ask Alexa as you think of items
3. **Partner on phone:** They can add via Todoist app anytime
4. **Mirror updates:** Items sync within 1-2 minutes
5. **Completed items:** They fade out when checked in Todoist

## Limits & Notes

- Alexa can only add items (not check them off via voice)
- Items must be checked off in Todoist app or on mirror
- Free Todoist works perfectly for this
- No special hardware needed beyond Alexa device
- Works best with Todoist Free or Premium

---

**You're all set!** Now you can manage your grocery list by voice, phone, and mirror! 🎉
