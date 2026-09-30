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

### Students

#### Adhith
**User Type:** Student

**Goals / Needs**
- Wants the application to be intuitive and easy to understand without requiring prior technical knowledge.
- Wants generated slides to summarize spoken information into concise, readable points.
- Wants generated presentations to include relevant images and diagrams that help communicate the subject visually.
- Wants the presentation to remain organized when the speaker transitions between different topics.

**Problems / Frustrations**
- Did not initially know how to start using The Slide Machine because the process was not intuitive to him as a first-time user.
- Felt that the generated slides could have included more images and diagrams.
- Found that a large amount of spoken information could be condensed into only a small number of bullet points, potentially leaving out useful detail.
- Experienced a major context switch from pickleball to League of Legends that caused The Slide Machine to begin generating content around the new topic, showing that topic changes can substantially alter the direction of the generated deck.

**Observations While Using The Slide Machine**
- Successfully gave an unscripted presentation involving both pickleball and League of Legends.
- The Slide Machine recognized his transition between the two subjects and changed the generated content accordingly.
- He liked the formatting of the generated slides.
- He liked how the application transformed his speech into succinct bullet points.
- He wanted the generated deck to make greater use of visual material such as images and diagrams.


#### Aidan
**User Type:** Student

**Goals / Needs**
- Wants slides to generate quickly so that presentations can be created efficiently, especially when working under a deadline.
- Wants generated slide content to be accurate and emphasize the most important information from the presentation.
- Wants greater control over how information is arranged and formatted so that the generated presentation matches how he wants to communicate his ideas.
- Wants to easily modify individual slide elements, including text and images, without having to regenerate an entire slide.
- Wants generated slides to remain visually and structurally consistent as the presentation moves between different topics.
- Wants a wider variety of slide layouts and formatting options so that presentations can be customized for different purposes.
- Wants the overall process to require as few manual corrections and edits as possible.
- Wants The Slide Machine to be fast and easy enough to use as an alternative to traditional presentation tools.

**Problems / Frustrations**
- Generated content may require manual corrections when the information is inaccurate or does not emphasize the intended points.
- Limited control over the arrangement of generated content can make it difficult to match the presentation to the speaker's intended structure.
- Editing individual parts of a generated slide can be inconvenient if making a small change requires regenerating more of the slide than necessary.
- Limited layout and formatting choices can restrict how much the presentation can be customized.
- Generated images may not always match the speaker's intended visual, creating a need to replace or modify them.
- Topic changes can create inconsistencies that require the speaker to manually reorganize or adjust slides.
- Repeated manual edits reduce the time-saving benefit of automatically generating a presentation.
- Speed and ease of use are particularly important when creating a presentation under a deadline.

### Instructors

#### Thanos Papadimitriou
**User Type:** Instructor

**Goals / Needs**
- Wants important concepts and instructional details from his lecture material to be preserved when slides are generated.
- Wants generated slides to maintain the logical structure and progression of the concepts he teaches.
- Wants students to retain access to deeper explanations and context even when generated slides summarize the lecture into concise points.
- Wants specific terminology, frameworks, and distinctions used in his course to remain accurately represented in generated materials.
- Wants visual frameworks, examples, and supporting material to remain connected to the concepts they are intended to explain.
- Wants generated course materials to remain useful to students after the lecture as a resource for reviewing and understanding what was taught.

**Problems / Frustrations**
- A large amount of detailed instructional material can be compressed into a much smaller number of generated slides, potentially removing useful context.
- Distinct concepts can be combined into broader summaries, reducing the level of detail available to students after class.
- Concise generated slides may not contain enough explanation for a student who did not fully understand a concept during the lecture.
- Important relationships between concepts, examples, and frameworks may become less clear when the original material is summarized.
- Students relying only on the generated deck may have difficulty recovering details that were present in the original lecture material but omitted from the slides.
- Additional AI explanations could create confusion if they do not remain consistent with the terminology and frameworks used by the instructor.

#### Katherine
**User Type:** Instructor

**Goals / Needs**
- Wants the system to capture important details from spoken ideas while removing unnecessary filler and "brain fog."
- Wants generated presentations to organize ideas into a logical structure even when the speaker presents their thoughts out of order.
- Wants an opportunity to review and rearrange the presentation structure before the system commits to generating the final slides.
- Wants the system to prioritize producing a well-structured presentation the first time rather than requiring repeated manual edits afterward.
- Is willing to accept additional generation latency if it results in a more accurate and logically organized final presentation.

**Problems / Frustrations**
- Speaking naturally or "brain dumping" does not always produce ideas in the order they should appear in a presentation.
- The generated deck can preserve an awkward ordering of ideas rather than recognizing how they should logically be organized.
- Topic transitions can be lost, causing later slides to feel disconnected or random compared with earlier material.
- The system moves too directly from spoken thoughts to finished slides, with little opportunity to reorganize the structure in between.
- Rearranging the presentation after generation can require unnecessary editing that could have been avoided before slide creation.

## Product Vision Statement

See instructions. Delete this line and place your Product Vision Statement here — one sentence describing the improvements and new features your team is proposing for The Slide Machine.

## User Requirements


### Student User Stories — Interview 1

1. As a student, I want clear instructions when I first open a shared lecture so that I know how to navigate and use the lecture materials.
2. As a student, I want lecture slides to clearly indicate when the instructor has changed topics so that I can follow transitions during the lecture.
3. As a student, I want different topics to be clearly separated in the generated slides so that I can easily find information about a specific topic later.
4. As a student, I want to navigate between sections of a lecture by topic so that I can quickly revisit the material I need to study.
5. As a student, I want important concepts to include relevant images or diagrams so that I can understand information that is difficult to learn from text alone.
6. As a student, I want diagrams to appear alongside the concepts they explain so that I can connect the visual representation with the instructor's explanation.
7. As a student, I want to view additional details behind a summarized bullet point so that important information from the instructor's explanation is not lost.
8. As a student, I want to distinguish between the instructor's main points and supporting details so that I know what information is most important while still having access to the full explanation.
9. As a student, I want to access the instructor's original explanation for a generated slide so that I can review context that may have been removed when the lecture was summarized.
10. As a student, I want the generated lecture materials to preserve important details even when the slides are concise so that I can study from them without missing material that was taught in class.

### Student User Stories — Interview 2

1. As a student, I want slides to generate quickly so that I can finish my presentation when I am short on time.
2. As a student, I want the information on my slides to be accurate so that I do not have to correct mistakes myself.
3. As a student, I want to control how information is arranged on my slides so that the presentation matches how I want to explain it.
4. As a student, I want the slides to stay consistent when I change topics so that I do not have to reorganize them myself.
5. As a student, I want to easily edit individual parts of a slide so that I do not have to regenerate the entire slide.
6. As a student, I want the AI to understand which information is most important so that my slides emphasize the right points.
7. As a student, I want more choices for slide layouts and formatting so that I can customize my presentation.
8. As a student, I want to choose or change generated images easily so that the visuals better match my presentation.
9. As a student, I want the presentation tool to require fewer manual edits so that I can create slides more efficiently.
10. As a student, I want the presentation tool to be as fast and easy to use as other presentation tools so that I can choose it when I am working under a deadline.

### Instructor User Stories - Interview 1

 1. As an instructor, I want the system to capture the important details from my speech so that useful information is preserved even when I speak informally.

2. As an instructor, I want the system to remove unnecessary filler from my speech so that the resulting presentation remains clear and focused.

3. As an instructor, I want the system to recognize when my ideas were spoken out of order so that the generated presentation still follows a logical structure.

4. As an instructor, I want related ideas to be grouped together so that the presentation does not feel disorganized when my spoken thoughts jump between topics.

5. As an instructor, I want transitions between different topics to be preserved so that students can understand how one part of the presentation connects to the next.

6. As an instructor, I want to preview an outline of my presentation before the final slides are generated so that I can verify the overall structure.

7. As an instructor, I want to rearrange topics in the generated outline before slide creation so that I can correct the order without manually editing many finished slides.

8. As an instructor, I want to approve the organization of my presentation before final generation so that the resulting slides better reflect how I intended to teach the material.

9. As an instructor, I want the system to prioritize getting the presentation structure correct on the first generation so that I do not have to repeatedly edit the final deck.

10. As an instructor, I want the option to trade additional generation time for better organization so that I can prioritize presentation quality when speed is less important.

### Instructor User Stories - Interview 2
1. As an instructor, I want generated slides to preserve the key concepts from my lecture so that students do not lose important information when my teaching is summarized.

2. As an instructor, I want students to have access to the deeper explanations behind concise generated slides so that they can recover context that could not fit on the slide itself.

3. As an instructor, I want students to be able to ask questions about concepts they do not understand so that confusion can be addressed after the lecture.

4. As an instructor, I want answers to student questions to use my actual lecture material so that explanations remain consistent with what I taught in class.

5. As an instructor, I want students to be able to ask follow-up questions about an explanation so that they can progressively work through concepts they are struggling to understand.

6. As an instructor, I want students to be able to ask for a concept to be explained in a different or simpler way so that students with different levels of understanding can still learn from my material.

7. As an instructor, I want AI-generated explanations to preserve the terminology, frameworks, and examples used in my lecture so that students are not taught conflicting versions of course concepts.

8. As an instructor, I want students to be able to trace an AI-generated explanation back to the relevant lecture material so that they can review the original context behind the answer.

9. As an instructor, I want the system to identify when a student's question was not addressed in my lecture so that the AI does not incorrectly present outside information as something I taught.

10. As an instructor, I want supplemental AI knowledge to be clearly distinguished from information taken from my lecture so that students understand what was actually covered in class.

11. As an instructor, I want control over whether the AI can supplement my lecture with outside knowledge so that I can determine how closely student explanations should remain grounded in my course.

12. As an instructor, I want students to continue learning from my lecture materials after class so that the generated deck functions as more than a static summary of the presentation.

## Activity Diagrams

<img width="415" height="595" alt="Screenshot 2026-09-30 at 2 34 42 AM" src="https://github.com/user-attachments/assets/bdc08c1d-a702-4f12-b1e7-c1ee726aacdf" />
<img width="414" height="593" alt="Screenshot 2026-09-30 at 2 34 48 AM" src="https://github.com/user-attachments/assets/210fb846-35fb-487e-9fa1-96a82442731a" />


## Wireframes

<img width="6120" height="12200" alt="Instructor screens - start at Lecture complete" src="https://github.com/user-attachments/assets/3b5af288-b75a-448b-8ba4-cafc7a75f641" />

## Clickable Prototype

https://www.figma.com/proto/3RlFLiHChOGwHDnM63JIcM/The-Slide-Machine-%E2%80%94-Instructor-Wireframes---UML?node-id=43-659&t=vVFPLaibprTOmkK8-1&scaling=min-zoom&content-scaling=fixed&page-id=43%3A624&starting-point-node-id=43%3A1777

## Stakeholder Demo

See instructions. Delete this line and place a link to the deck The Slide Machine generated during your presentation here, after you have presented.

## Exit Ticket

See instructions. Delete this line and place a link to the exit-ticket quiz you generated from your demo deck and distributed to the class, along with a short note on what — if anything — you had to correct in the generated questions before publishing.
