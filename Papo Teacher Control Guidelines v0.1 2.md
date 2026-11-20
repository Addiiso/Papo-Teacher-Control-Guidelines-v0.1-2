# Keeping Teachers in Control: Design Guidelines and an Evaluation Checklist for AI Lesson Tools

**Version 0.1 · November 2026**  
**Kehinde Adisat Olawuyi**  
Product designer and education technology researcher, San Francisco

---

## Why I wrote this

Teachers are already using AI to prepare lessons. In a Gallup survey of 2,232 U.S. public K-12 teachers in spring 2025, more than a third said they use AI at least monthly to prepare to teach, and 28 percent said they use it to modify materials for their students' needs. Only 19 percent said their school had a policy on AI.

That gap is what this document is about. Most of the conversation about AI in classrooms stops at "teachers should review what the AI produces." I agree, but in practice that sentence hides the hard part. A generated lesson might have one wrong step, an activity that needs materials the room does not have, or an explanation pitched at the wrong level. Whether a teacher can catch and fix those things in the ten minutes they have depends almost entirely on how the tool is designed.

These guidelines describe what that design should look like. They come out of my own research and testing, and they are written for two groups: the people who build AI lesson tools, and the school and district staff who have to decide which ones to buy.

This is an early version. It is based on a small study, and I say more about its limits below.

## Where this comes from

My master's thesis at San Francisco State University, *Equity Design and Generative AI: Reimagining Access to Differentiated Learning Resources*, looked at why it is so hard for elementary teachers to prepare materials that work for every student in the room. I spoke with educators and education organizations about where lesson preparation breaks down, and then designed Papo, a prototype tool for elementary teachers.

Papo takes a learning objective and drafts a lesson that pairs a short explanation with a hands-on activity. My test case was a first-grade fractions lesson in which students use physical materials to see how parts make up a whole. The teacher reviews and edits the draft before using it.

I tested two layouts of the prototype with [number] participants [describe briefly, for example: elementary educators]. Participants were asked to create lesson materials for the fractions lesson, edit the dashboard, and download their instructional aids. A few things stood out:

- **Editing was the biggest problem.** Every participant struggled when they tried to change what had been generated. This was the clearest result of the whole study.
- Participants finished the main task faster with one layout than the other (an average of 137 seconds versus 184 seconds), which told me that the structure of the screen matters a great deal.
- Participants wanted to see when each resource had been created.
- Some of my interface wording was unclear to them.
- The download step did not make it obvious what files they were getting.

None of these are surprising on their own. Together, they pointed to a simple idea: reviewing AI output is not something that happens after the tool is done. It has to be designed into the tool.

## Six guidelines

### 1. Break the lesson into parts a teacher can change one at a time

A generated lesson should arrive in clear sections, such as the objective, the explanation, the activity, the materials list, and a quick check for understanding. Each section should be editable on its own, and the teacher should be able to ask for a new version of one section without losing the rest.

*Why:* When a lesson comes back as one block of text, a single problem forces the teacher to either regenerate everything or rewrite it by hand. My participants' trouble with editing came largely from this.

*In practice:* If the fractions activity calls for fraction tiles and the class does not have any, the teacher should be able to fix just the activity and leave the explanation alone.

### 2. Keep the learning objective in view while editing

The objective should stay visible on the screen the whole time a teacher is changing the lesson.

*Why:* Small edits add up. A teacher who swaps one activity for another can end up, without meaning to, with a lesson that no longer teaches what it was supposed to. Keeping the goal in view makes that drift easier to notice.

*In practice:* The objective is pinned at the top of the editing view. A later version of Papo will also point out when an edited section no longer seems to match the objective. I have not tested that feature yet.

### 3. Let teachers change materials, not just wording

Teachers should be able to tell the tool what they actually have in the room and get an activity built around it.

*Why:* Hands-on learning is valuable, but only if the materials exist. Many AI tools assume a well-stocked classroom. A teacher with paper strips and a box of buttons needs an activity that uses paper strips and buttons.

*In practice:* The teacher can list available materials before generating, or substitute a material afterward. The activity is then rewritten around the new material while keeping the same purpose.

### 4. Let teachers decide what the AI draws on

Teachers should be able to add their own context, such as previous lesson notes, and see what the tool used when it produced a draft.

*Why:* A teacher knows what the class learned last week, how their curriculum phrases things, and what has worked before. A tool that ignores that context produces generic lessons that take longer to fix. Letting teachers supply the context also makes it clearer where the content came from.

*In practice:* In Papo, a teacher can upload past lesson notes, which the tool uses as direct context for new lessons.

### 5. Nothing reaches students until a teacher approves it

The tool should require a clear approval step before a lesson can be printed, shared, or downloaded. Each lesson should show when it was created and last edited, and the download step should state exactly what the teacher is getting.

*Why:* This turns "teachers should review AI output" from a hope into a feature. The creation dates and clearer downloads respond directly to what my participants asked for.

*In practice:* A lesson stays in draft until the teacher marks it approved. Drafts and approved lessons look different on screen.

### 6. Learn from edits without collecting student data

The tool should record which sections teachers change and, where the teacher is willing, a short reason, such as "wrong level," "materials not available," or "factual error." It should not collect personal information about students.

*Why:* The places where teachers keep correcting the AI are the places where it fails. Tracking them is how a tool, and the people evaluating it, find out where to look. This can be done entirely without student data, in line with federal privacy expectations for education technology.

*In practice:* Each edit is logged against the lesson section, not against any student.

### Two smaller lessons from testing

- **Use plain words.** Some of my labels made sense to me and not to teachers. Interface wording should be tested with teachers, not assumed.
- **Accessibility is part of control.** A teacher can only adapt a lesson for a student with a disability if the tool's output can be adapted. Generated materials should be available in accessible formats, and the tool itself should meet the Web Content Accessibility Guidelines (WCAG) 2.2 at Level AA. I have not yet completed a formal accessibility review of Papo, and that review comes before any classroom pilot.

## Checklist: questions a school can ask before choosing an AI lesson tool

A "no" to any of these does not have to rule a tool out, but it tells you where teachers will have to work around it.

1. Can a teacher edit one part of a generated lesson without regenerating the whole thing?
2. Does the learning objective stay visible while the teacher edits?
3. Can the teacher tell the tool what materials the classroom has, and get activities built around them?
4. Can the teacher add their own lesson notes or curriculum as context?
5. Can the teacher see what the tool drew on when it produced a lesson?
6. Is teacher approval required before anything is printed, shared, or given to students?
7. Does each lesson show when it was created and last edited?
8. Can generated materials be exported in accessible formats, such as text a screen reader can read and images with descriptions?
9. Has the tool been reviewed against WCAG 2.2 Level AA, and will the vendor share the results?
10. Does the tool work without collecting personal information about students?

## What this version does not do yet

I want to be clear about the limits. These guidelines come from one study with a small number of participants, using a design prototype rather than working software. They have not yet been tested in a classroom with students, and Papo has not yet had a formal accessibility review. Some guidelines, especially the second and sixth, describe features I have designed but not yet tested.

## What comes next

I am now building a working version of Papo that puts these six guidelines into practice. The next step is a classroom pilot in spring 2027, in which teachers will use it to prepare and teach real lessons. I will measure how long it takes to reach a lesson they are willing to use, which parts they change and why, and whether they can make changes without losing the objective. Version 1.0 of these guidelines will be revised based on what the pilot shows, and I plan to submit the findings for peer review.

If you are a teacher, a school leader, or a developer and you would like to try the checklist or share what you are seeing in your own classroom, I would be glad to hear from you at [your email address].

## How to cite

Olawuyi, K. A. (2026). *Keeping Teachers in Control: Design Guidelines and an Evaluation Checklist for AI Lesson Tools* (Version 0.1). [Link where published]

This document is shared under a Creative Commons Attribution 4.0 International license (CC BY 4.0). You are free to use and adapt it with credit.

## References

- CAST. (2024). *Universal Design for Learning Guidelines* version 3.0. https://udlguidelines.cast.org
- Carbonneau, K. J., Marley, S. C., & Selig, J. P. (2013). A meta-analysis of the efficacy of teaching mathematics with concrete manipulatives. *Journal of Educational Psychology, 105*(2), 380 to 400.
- Gallup & Walton Family Foundation. (2025). *Teaching for Tomorrow: Unlocking Six Weeks a Year With AI.*
- Olawuyi, K. A. (2025). *Equity Design and Generative AI: Reimagining Access to Differentiated Learning Resources* (Master's thesis). San Francisco State University.
- U.S. Department of Education. (2025, July 22). *Guidance on the Use of Federal Grant Funds to Improve Education Outcomes Using Artificial Intelligence (AI).*
- World Wide Web Consortium. (2023). *Web Content Accessibility Guidelines (WCAG) 2.2.* https://www.w3.org/TR/WCAG22/
