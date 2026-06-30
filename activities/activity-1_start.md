# Activity 1: Warm-Up — Curve Diagnosis

> ⏱️ **This is a warm-up — 15 minutes total.** There is nothing to install or submit. The goal is to arrive in the room, reconnect with your cohort, and start thinking.

> 📋 **Open your worksheet now:** This activity maps to **Part A** of [`Activity_Worksheet.md`](../handouts/Activity_Worksheet.md). Open it in your Jupyter file browser (left sidebar) or in a text editor alongside this file. You will record your curve diagnoses there — it is your evidence document for the day and feeds directly into Task 6.

**Primary KSB:** B3 — Acts inclusively when collaborating with people from technical and non-technical backgrounds. Contributing to knowledge sharing, management and empowerment across the broader team.

🎯 **Learning Objective:** Read training curves and begin connecting the diagnostic vocabulary to patterns you already recognise

## 📋 Expected Outputs

- A brief catch-up with your group
- Each curve matched to its most likely cause
- A one-sentence explanation of one unhealthy curve, suitable for a non-technical colleague

---

## 📝 Task 1 — Catch Up (5 minutes, groups of 2–4)

Spend no more than 5 minutes. Go round the group and answer one question each:

> "What have you been working on since the last workshop — in your job, not your coursework?"

No deep dives. The point is to reconnect and to notice the range of contexts in the room.

# **My Answer**: 
I've been researching what personal hardware I can invest in to run local models and avoid subscription / vendor lock-in when the prices jump up too high in the future! A 5090 with 32GB of ram is crazy expensive but I might be able to invest ina 5080 or 5070ti with 16GB ram!

---

## 📝 Task 2 — Match the Curves (5 minutes, groups of 2–4)

Your coach will display the three training curve images from the `assets/` folder.

For each curve, agree as a group on the most likely cause before moving on.

# **My Answer**: 

| Curve | What you observe | Most likely cause |
|---|---|---|
| A | It looks like a gradual drop for both the training and validation loss with a small gap between them.  | The training and validation performance can keep up with each other causing an example of a good learning curve with a balanced generalization gap.
| B | It looks unstable, spikes are going up and down and never steady | High learning rate, it is running before it can walk.
| C | It looks similar curve a at a glance with val loss being higher and close enough to training loss, however the Y axis is zoomed in and misleading, there is a big difference between ~0.6 drop (from curve a) and ~0.1 drop (from curve c)  |Low learning rate, it's going in the right direction but at a snails pace.|

💡 **Tip:** Focus on what the *validation* line is doing relative to the *training* line — not just whether training loss is going down.

📋 **Thinking further (no image needed):** The worksheet has a fourth scenario — training loss barely moves at all, and *neither* does validation performance. This is a different failure mode from the three curves above: the model is not overfitting (validation is fine), it is simply not learning at all. What would you check first? Write your answer in **Question 4 of Part A** of the [Activity Worksheet](../handouts/Activity_Worksheet.md). Common causes include a learning rate so low the weights barely update, a frozen layer that should be trainable, or a bug in the training loop.

✅ **Checkpoint:** You have a written cause for each curve, and a written answer to Question 4, before your coach reveals the answers.

---

## 📝 Task 3 — What Felt Familiar? (3 minutes)

Your coach will have just shown a slide with examples of these same three patterns appearing outside machine learning — in medicine, economics, sport, and management.

Look back at those examples. Without hunting for a perfect parallel, answer this question as a group:

> "Which of those examples felt closest to something you've encountered in your own work — and why?"

You do not need a technically precise match. A rough recognition is enough. Share briefly; one sentence each if time is short.

📘 **Why this matters:** The patterns you are about to see in a training loop — too cautious, too aggressive, and just right — are not ML-specific. Recognising them in your own domain means you will have stronger intuitions when you see them in the notebook, and you will be able to explain them more naturally to colleagues who do not have an ML background.

# **My Answer**: 
I have not dealt much with training data directly but I have dealt with confidence thresholds for security and compromise events, for example Microsoft Defender for Identity alerts learns user beheaviour data over time which acts as a baseline for triggering incidents, some events have a threshold you can configure because they are too sensitive and cause too much noise. 

High is the default value, and applies standard thresholds to reduce false positives.
Medium and Low thresholds increase the number of alerts generated by Defender for Identity. 

---

## 📝 Task 4 — Plain Language Explanation (2 minutes)

Choose **one** of the unhealthy curves. Write one or two sentences explaining what is happening and what you would recommend — addressed to a non-technical colleague, with no jargon.

> _______________________________________________________________

📘 **B3 note:** The goal is not to simplify — it is to translate accurately, so the other person can participate in the decision rather than just defer to you. A good explanation gives them something actionable.

# **My Answer**: 

I have chosen curve b, this was the learning rate was too high. The learning rate dictates your step size, if the step is too massive, instead of walking steadidly down to the bottom of the hill, the model takes giant leaps and overshoots the valley entirely. It ends up jumping so high that the math simply breaks down.

---

🎓 **Complete** — proceed to [Activity 2](activity-2_start.md)
