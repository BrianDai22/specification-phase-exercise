# Specification Phase Exercise

## Team members

- [Brian](https://github.com/briandai22)
- [Mihir](https://github.com/mihirgan06)
- [Yash](https://github.com/yash-pandya9798)
- [Linh](https://github.com/katiettran)
- [Theo](https://github.com/theoegoldstine)

## Review of the Current Application

These findings come from Brian, Mihir, and Linh testing the app.

### Strengths

| Area | What we noticed |
| --- | --- |
| Real-time slides | The app transcribed our speech and created slides that followed the selected template. |
| Filler filtering | Saying something like "does that make sense?" did not add unnecessary text to the slide. |
| Topic changes | Speaking about the same topic added to the current slide. Moving from MergeSort to its performance created a new slide. |
| Formatting | Titles and fonts stayed consistent across the slides. |
| Understanding context | Saying "the planet closest to the Sun" produced Mercury without us naming it. |
| Spanish | The app understood Spanish speech and captured the main point. |
| Images | A MergeSort example included a relevant diagram with a source citation. |
| Quizzes | The questions matched the lecture and had clear answer choices. |

### Weaknesses

| Area | What we noticed |
| --- | --- |
| Missing details | Longer explanations were sometimes shortened too much, leaving out important information. |
| Quick topic changes | Switching topics quickly sometimes caused the app to miss the new content. |
| Corrections | Correcting an earlier statement created a new slide instead of fixing the original one. |
| Live transcript | The small gray transcript disappeared quickly, so we could not look back at earlier speech. |
| Setup | It was unclear what settings we could configure, and we did not find a tutorial during first use. |
| Microphone | It was unclear whether the mic was ready until the transcript started appearing. |
| Quiz difficulty | The wrong answers were often too obvious. |
| Image loading | Images were slow to appear and did not appear consistently. |
| Specific examples | Asking for a step-by-step MergeSort diagram using a specific array produced a general published diagram instead. |
| Conflicting information | When speech and seed material disagreed, one test followed the speech and another followed the seed. |

### Gaps

| Area | What we noticed |
| --- | --- |
| Refinement instructions | Refinement worked on a second attempt, but we could not type a request like "make the wording simpler and use less jargon." |
| Spoken quiz requests | Asking for a quick multiple-choice check did not create one. We had to access quiz creation separately. |

## Prior Art & Originality

### What we checked

We reviewed the [background](background.md), [specification](https://github.com/bloombar/slide-machine/blob/better-faster/docs/SPEC.md), including Future Work and Open Questions, [roadmap](https://github.com/bloombar/slide-machine/blob/better-faster/docs/ROADMAP.md), open [issues](https://github.com/bloombar/slide-machine/issues) and [pull requests](https://github.com/bloombar/slide-machine/pulls), and [source code at d340bf5](https://github.com/bloombar/slide-machine/tree/d340bf5cadf96c46e4115a917c0539f51e5ac7b1) on September 28, 2026.

### What already exists

The app already has transcripts and slide editing. [EDIT-6](https://github.com/bloombar/slide-machine/blob/better-faster/docs/SPEC.md#edit-6-spoken-transcript-editing) covers editing a slide's spoken transcript. [GEN-4](https://github.com/bloombar/slide-machine/blob/better-faster/docs/SPEC.md#gen-4-post-lecture-ai-reformat-holistic-regeneration) already specifies using the full transcript to refine slides, reconcile corrections, and preview and accept changes. [Future Work](https://github.com/bloombar/slide-machine/blob/better-faster/docs/SPEC.md#18-future-work) also includes editing decks through conversations with an external AI agent. We are not claiming these features as new.

### Our proposed addition

We want students to talk through a lecture with an AI voice assistant after class. It would use the slides and transcript, along with any seed material the professor approves. Students could speak or type a question and ask follow-ups until the explanation makes sense. Answers would point back to the lecture material. This would also reuse the realtime model being used to generate the slides from the transcript so there would not be a new client to connect to the current slide machine.

For example, a student could ask, "Walk me through the MergeSort example from class," then request a similar problem to try with hints.

The professor controls access to the materials and sets usage limits. Students would not receive the API key or be able to change the lecture through the assistant. Student personal information will also stay out of external models with strict filtering. When the materials do not support an answer, the assistant should say so.

Our proposed contribution is letting students study through a conversation about their actual lecture. The app already reads slides aloud and generates quizzes. Its existing AI-assistant integration helps authors edit decks. Neither provides this student study experience, which we did not find in the project materials or GitHub history we reviewed. Interviews will test whether students need it before we finalize the scope.

## Stakeholders

See instructions. Delete this line and replace with the name(s) of the stakeholder(s) you interviewed and lists showing their goals/needs, and problems/frustrations. Note which type of user each stakeholder represents. You may use pseudonyms or partial names to maintain their privacy, but you must privately share their full names and contact information as part of your submission of this exercise

## Product Vision Statement

See instructions. Delete this line and place your Product Vision Statement here — one sentence describing the improvements and new features your team is proposing for The Slide Machine.

## User Requirements

See instructions. Delete this line and place a list of your User Stories here, grouped by type of user. These should describe functionality that is new or changed, not functionality the app already has.

## Activity Diagrams

See instructions. Delete this line and place images of your UML Activity diagrams here, each with the text of the user story it illustrates.

## Wireframes

See instructions. Delete this line and place your wireframe diagrams here, covering every new screen and every existing screen your proposal changes, for every type of user.

## Clickable Prototype

See instructions. Delete this line and place a publicly-accessible link to your clickable prototype here.

## Stakeholder Demo

See instructions. Delete this line and place a link to the deck The Slide Machine generated during your presentation here, after you have presented.

## Exit Ticket

See instructions. Delete this line and place a link to the exit-ticket quiz you generated from your demo deck and distributed to the class, along with a short note on what — if anything — you had to correct in the generated questions before publishing.
