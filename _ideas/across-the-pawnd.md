---
title: "Across the Pawnd"
excerpt: "A private two-person digital world that helps long-distance friends and couples stay connected through daily adventures, messages, shared spaces, and playful rituals."
collection: ideas
permalink: /idea-lab/across-the-pawnd/
idea_order: 1
status: "Working prototype"
---

**Across the Pawnd** is a private interactive world for two people living on opposite shores. I created it for long-distance best friends and couples who want more than another messaging app: a small shared place that makes staying connected feel playful, intentional, and emotionally present.

The experience represents each person as a pup on one side of a pond. After creating a private Pawnd with a shared room code and password, both people enter the same synchronized world. They can complete small daily adventures, send messages across the water, decorate a room together, and build a visible record of ordinary moments shared across distance.

### The inspiration

Long-distance relationships often depend on messages, video calls, and calendars. Those tools are useful, but they can make connection feel scheduled or transactional. Across the Pawnd explores a softer question:

> What if two people separated by distance could still inhabit a tiny shared world?

The project turns small acts—answering a prompt, sending a photo, tapping a paw, choosing a mood, or placing a piece of furniture—into shared rituals. The goal is not to replace conversation. It is to create more gentle reasons to think of one another and more artifacts of the relationship to look back on.

### Core experience

The working prototype includes:

- **Private two-person Pawnds:** each shared world has its own room code and PBKDF2-hashed password, with isolated room data and signed sessions.
- **A 50-day adventure:** one curated activity appears each day, encouraging the two people to share, create, notice, or do something together.
- **A shared star jar:** completed daily activities add collectible stars and create a visible record of progress.
- **Messages in bottles:** either pup can send text or compressed photos across the pond, where the bottles float and can be opened individually.
- **Two identities and two shores:** each person chooses their pup identity, name, city, and timezone; the scene reflects local time, day or night, and live weather.
- **A shared little room:** earned hearts can be used to choose furniture and decorations, then place, resize, and layer them in a synchronized room.
- **Seven real-time two-player games:** short games give the pair another lightweight way to spend time together.
- **Small emotional gestures:** paw taps, mood pebbles, answer reveals, together-task markers, and shared rewards make everyday interaction feel tangible.
- **Adaptive atmosphere:** original instrumental music changes with the selected shore’s local time and weather, with responsive layouts for desktop and mobile.

### Design approach

Across the Pawnd uses a calm illustrated landscape rather than a conventional dashboard. The pond, two shores, pups, floating bottles, star jar, and shared room turn relationship data into a place with emotional meaning.

Several design principles guide the project:

- **Private by default:** each Pawnd belongs to only two people.
- **Low-pressure connection:** most interactions are small enough to fit into a busy day.
- **Reciprocity:** both people contribute to tasks, messages, rewards, and the shared room.
- **Visible continuity:** stars, bottles, hearts, and room objects show that the relationship is being built over time.
- **Distance-aware design:** local clocks, weather, timezones, and daily reset rules acknowledge that the two people may be living very different days.

### Technical implementation

The prototype uses HTML, CSS, and JavaScript for the interactive client and a Python server for shared state and room authentication. Room progress is stored in isolated server-side files, while identity remains in each person’s browser. The deployed version uses Render and is designed around a persistent storage model so shared progress can survive restarts and deployments.

For larger public use, the next technical step would be moving room records and photo data to a managed database and object-storage service.

### Links and materials

- [Open the live Across the Pawnd experience](https://across-the-pawnd.onrender.com/)
- [View the source code and project documentation on GitHub](https://github.com/belladai36/across-the-pawnd)
