# How Khadijah was engineered

This page is the proof that Khadijah was built with a process. The program itself isn't published; the process is open.

## Who did what

- **Rafiq: architect and product owner.** The vision, the requirements, the decisions, the standards, and the sign-off on every piece of work.
- **Claude, an AI coding assistant: implementation.** The code, written under the requirements and rules above, and checked by tests and automatic checks.

The skill on show is directing AI to build a large, tested, documented system, and holding it to a standard.

## Six working rules

1. Work follows a plan agreed before anything is built.
2. Requirements are written down and fixed first. A new idea goes on a change list, not into the build.
3. Every requirement has a test, written before the build.
4. Nothing is called done until it has been checked against its requirement and the result shown.
5. Every document has a purpose, an owner and a version, and each fact lives in one place.
6. Every change is recorded and versioned.

## Standards used as references

These are the references the project's plans, requirements, architecture, tests and documents were written against. They are used as references. The project is not certified to any of them, and the editions were confirmed by catalogue lookup on 2026-11-01 (the standards themselves are paid documents).

| Standard | Used for |
|---|---|
| ISO/IEC/IEEE 12207 (2026) and 24748-3 | Software life cycle and guidance on applying it: the build plan |
| ISO/IEC/IEEE 29148 | Requirements: how the 650+ requirements are written |
| ISO/IEC/IEEE 42010 | Architecture description |
| ISO/IEC 25010 | Quality characteristics: reliability, security, usability and the rest |
| ISO/IEC/IEEE 29119 | Software testing: the test plan and the test cases |
| ISO/IEC/IEEE 15289 and 26514 | Content of project documents, and documents for users |
| ISO/IEC 29110 | Software engineering for very small teams |
| ISO/IEC 5055 | Automated source code quality measures |
| PEP 8 and PEP 257 | Python style and docstrings |
| Semantic Versioning, Keep a Changelog, Conventional Commits | Version numbers, the changelog and commit messages |

## Evidence

- **650+ written requirements** and **800+ test cases**, linked so every requirement points to its tests.
- **1,400+ automated tests**, run before work is called done.
- **95 recorded decisions** on a change list: who asked, what was decided, what was built.
- **15 project documents** with a purpose, an owner and a version each, plus a 23-page user guide written for the person who uses her.
- **Checks on every change:** a document checker (every file, link and name a document mentions must exist), a style checker, a secret scan, and a requirement-to-test check. A change that fails them does not get committed.
- **644 changes in the 12 days of this rebuild** (1 to 12 November 2026), each in the standard commit format.

## A real example, start to finish

While recording the demo, the review caught a wrong answer: asked to read the task list when there were no open tasks, she said "I don't have a task list in my data". That is wrong, because there were simply no open tasks.

1. **Written down:** a new entry on the change list, with who asked and why.
2. **Requirement:** "When there are no open tasks and she is asked to read them, she shall say there are no open tasks, and never that she has no task list."
3. **Test first:** a test for that requirement was written and seen failing.
4. **Fix:** the smallest change that makes it pass.
5. **Shown:** the whole test suite (1,403 tests that day) ran green, and she answered correctly on the real screen: "Sir, you have no open tasks right now."

The same review also removed a demo question ("who won the Sixers game last night") because a web search could not give a reliable answer. A wrong answer in a demo is worse than no answer.

## A second example: a prompt is a request, not a guarantee

Her instructions tell her to answer in the language the owner used. In a test in Greek, "who are you" came back in English, because a fixed English sentence in the same instructions beat the language rule. That rule had passed in every other test.

1. **Found by probing the real assistant**, not by reading the instructions: the same Greek line was sent repeatedly, and only some answers were in Greek.
2. **Reworded the instruction.** It helped part of the time, which is the point: wording alone is not a guarantee.
3. **Added a safeguard in code, with tests written first.** A message in a non-Latin script now tells the model the language, and an answer that comes back in the wrong alphabet is translated once before it is spoken.
4. **Written down** as a change and a requirement, like everything else.

The lesson I took into the design: anything that must always hold is enforced by the structure and checked by a test, not left to the model's good behaviour.

## Honest limits

- She can't be run by visitors: her face, voice and keys are private, and she needs them.
- Answers from the web or an AI model can be wrong. That's why the process checks them, and why the demo shows only answers that were verified.
- The standards are references. Nothing here claims certification.
