# 📋 Todoist Grocery List Setup Guide

## What is Todoist?

Todoist is a task/todo list app that:
- ✅ Syncs across all devices (phone, web, mirror)
- ✅ Shared with your partner (both can add/edit items)
- ✅ Works with Alexa voice commands
- ✅ Perfect for grocery lists

## Step 1: Create a Todoist Account

1. Go to **https://todoist.com**
2. Sign up for a free account
3. Create a project called "Grocery List"

## Step 2: Get Your API Token

1. Go to **https://todoist.com/app/settings/integrations/developer**
2. Click **Create a new token**
3. Name it "MagicMirror"
4. **Copy the API token** - you'll need this

## Step 3: Share with Your Partner (Optional but Recommended!)

1. In Todoist, open your "Grocery List" project
2. Click the **Share** button
3. Add your partner's email
4. They'll get an invite and can add items too!

## Step 4: Update Your config.js

Replace in `config/config.js`:
```javascript
accessToken: "YOUR_TODOIST_API_TOKEN",  // Paste your token here
projects: ["Grocery List"],              // Name of your project
```

## Step 5: Verify It Works

1. Start MagicMirror
2. The mirror should show your Todoist tasks
3. Add an item in Todoist app (phone or web)
4. It will appear on the mirror within 1-2 minutes

## 🎤 Using Alexa to Add Items

### Enable Alexa Todoist Skill:

1. Open **Alexa app** on your phone
2. Go to **Skills & Games**
3. Search for **"Todoist"**
4. Click the official **Todoist** skill
5. Click **Enable**
6. Log in with your Todoist account
7. Select which projects Alexa can add to (choose "Grocery List")

### Voice Commands:

```
"Alexa, add milk to Grocery List"
"Alexa, add eggs to Todoist"
"Alexa, what's on my Grocery List?"
```

The items will appear in:
- ✅ Alexa app
- ✅ Todoist app/web
- ✅ **Your MagicMirror!**

## 📱 Both You and Your Partner Can:

- Add items from phones (Todoist or Alexa)
- Check items off as done
- See the list on the mirror in real-time
- Share notes with each other

## Layout

The grocery list appears in the **bottom_left** corner of your mirror, with:
- Task name
- Fading effect for completed tasks
- Auto-refresh every few seconds

---

## Troubleshooting

**Tasks not showing?**
- Verify API token is correct
- Project name must match exactly ("Grocery List")
- Restart MagicMirror

**Alexa not adding items?**
- Make sure Todoist skill is enabled
- Check you're using correct project name
- Items may take 1-2 minutes to sync

**Can't see shared list?**
- Partner must accept the share invite
- Verify both using same Todoist project
- Both need API tokens in their config (if running separate mirrors)

---

## Tips

- Keep project names simple (avoid special characters)
- Todoist Premium adds more features, but free tier works great
- Create multiple projects (Groceries, Household, Ideas, etc)
