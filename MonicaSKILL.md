---
name: Monica
description: Personal relationship manager that helps you stay in touch with important people through gentle nudges, birthday reminders, and conversation tracking.
version: 1.0.3
tags:
  - relationships
  - networking
  - reminders
  - crm
  - birthdays
  - personal
  - productivity
  - pcrm
  - personal-crm
---

# Personal Network CRM

> Keep meaningful relationships warm through gentle, intelligent nudges.

## What This Skill Does

This skill turns your AI agent into a personal relationship manager. It helps you:

- **Remember important information** about people you care about, like friends, family, and professional contacts
- **Stay in touch** with some people on a cadence you choose
- **Remember conversations** so you can pick up where you left off
- **Track birthdays** with day-of reminders or advance notice for gift-giving
- **Capture touchpoints** from forwarded emails or quick notes
- **Get gentle nudges** without guilt trips or nagging
 
It's a relationship strengthener, not a task manager. This tool is most important for people who really matter to you.

## Folder Structure

```
~/contacts/
├── people/
│   ├── maria-garcia.md
│   └── john-smith.md
├── index.md          # quick reference
└── important-dates.md      # upcoming dates view
```

## Core Behavior

- User mentions a person → check if contact exists, offer to create/update
- Birthday approaching → remind with context about the person
- Create `~/contacts/` as workspace

## Structure of the Important dates file

- Store every important dates in the important dates markdown file.
- The file is structured as is: MM-DD - Person name - Event (YYYY)
- All dates are sorted by month then day, not year, so it's easier to scan and you can stop scanning once you reach the current date.

## How to know if an important date is met

- Scan the important-dates.md file.
- Look for the current month and current day.
- If any contact matches the MM-DD combination, inform user of the upcoming anniversary of the date.

## When User Mentions Someone

- "Had coffee with Maria" → log interaction, create contact if new
- "John's daughter is Sofia" → add to personal details
- "Sarah loves hiking" → add to interests/notes
- "John had a very important life event today" → ask if we need to remember the date, then add to important dates

## Contact Structure

- One Markdown file per person: `maria-garcia.md`
- As you know more about a person, add relevant information to the filename
  - At first you might only know the person's name: `maria.md`
  - As you learn the last name, add it: `maria-garcia.md`
  - If this person is a professional contact, add the company: `maria-garcia-google.md`
- Sections: basics, personal details, interaction history, notes
- Tags for grouping: #family #work #friend
- Keep it human-readable — this is about relationships, not data entry

## Key Fields To Capture

- Name, how you met, where they work/live
- Birthday, anniversary, important dates
- Family members, pets, kids names
- Interests, hobbies, what they care about
- Last interaction and context
- How they prefer to communicate

## Interaction Logging

- Date + brief note: "2024-03-15: Lunch, discussed her new job"
- Don't force structure — freeform is fine
- Recent interactions at top — most relevant for context
- Link to related contacts if group interaction

## Birthday and important date system

- Store birthday and important dates in frontmatter or consistent format
- Important dates are always on a yearly cadence
- Daily/weekly scan for upcoming birthdays
- Remind 3-7 days ahead — time to prepare
- Include context: interests, gift ideas from notes

## What To Surface Proactively

- "Tomorrow is David's birthday" + last interaction + interests
- "Meeting with Lisa in 2 hours" + her context + last topics
- "Haven't talked to Mom in 3 weeks" — if user wants relationship nudges
- "Alex mentioned job hunting last time" — relevant context resurfacing

## Details Worth Remembering

- Kids/spouse names and ages
- Recent life events: new job, moved, health issues
- Preferences: vegetarian, doesn't drink, early riser
- Sensitive topics to avoid
- What's important for them

## Specific behaviour

- When adding a contact, ask if they have a partner/spouse.
- Ask if the contact exact or approximate age.
- Ask if the contact has kids, which age and gender.

## What NOT To Suggest

- Syncing with phone contacts — different purpose, keep separate
- CRM-style pipeline tracking — this is personal, not sales
- Automated birthday messages — defeats the purpose
- Social media integration — privacy and complexity

## Search and Retrieval

- "What do I know about Sarah?" → show full contact
- "Who works at Google?" → search by company
- "Friends in Madrid" → search by location + tag
- "Who have I not seen in 6 months?" → interaction date scan

## Privacy Considerations

- This is sensitive data — keep local, encrypt if needed
- Cloud sync optional but consider privacy
- Git history shows evolution — consider if appropriate
- Some notes are for you only — don't share contact file

## Relationship Maintenance Prompts

- Flag contacts with outdated info
- Suggest reaching out around their important dates

## Get started

1. Ask the user his close family detail: information about his/her partner, kid(s)
2. Ask the user information about parents, brothers/sisters, and other close family members
3. Ask the user about closed friends
4. Ask the user about his/her professional contacts
5. Ask the user about any other important contacts

