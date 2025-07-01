Dynamic Quiz Creator  

1. Objective 

To enable learners to assess their knowledge , helping them identify content that may be unnecessary for them to complete. This tool supports personalized learning paths, improves time efficiency, and empowers learners with greater control over their development journey. 

2. Background 

Given a document (e.g.a Go1 course, a video, etc.) a quiz can be generated that assesses competency. Basic options to edit/configure the quiz may be available based on the user’s role.  

3. Target Users 

Proof of concept for end learners and managers 

3.1 User Goals 

Skip unnecessary content based on existing knowledge 

Gain awareness of knowledge gaps 

Save time by focusing only on new material 

Track knowledge growth over time 

4. Features & Functionality (MVP) 

The goal of this PoC is to demonstrate that learners can take AI-generated quizzes built from structured content (HTML, PDF, video transcript), receive meaningful feedback by topic, and make informed decisions on whether to proceed with a course — all without needing manual quiz creation or advanced authoring tools. 

4.1 Quiz Types 

Multiple choice 

True/false 

Fill in the blank 

Short answer 

4.2 Quiz Generation 

AI-generated questions based on course content 

Authors can review/edit AI-suggested questions 

4.3 Quiz Access 

Appears on the course landing page (before learner starts the course) 

Optional for learners to take 

4.4 Quiz Results 

Displayed immediately after completion 

Breakdown by course topic/module 

Percentage score per topic 

4.5 Learner Profile Integration 

Quiz results stored in user profile 

Learners can view previous quiz attempts 

Quiz outcomes used to make personalized content recommendations 

5. Out of Scope for MVP 

Admin-level analytics or dashboards 

Integration with Go1 authentication or SSO 

API-based content ingestion from Go1’s course catalog 

In-depth content-skipping automation within courses 

6. Future Considerations (V2+) 

Admin dashboards showing learner performance trends 

Full LMS and user authentication integration 

Granular recommendations to skip specific course modules 

Multi-question formats (e.g., case studies, interactive scenarios) 

Integration with platform-wide progress tracking 

7. Success Metrics (MVP) 

% of learners who choose to take the quiz before starting a course 

Learner satisfaction and NPS related to quiz feature 

 

8. Dependencies 

Access to content for AI generation (initially via manual upload or ingestion) 

AI models capable of generating domain-relevant quiz questions 

9. Risks & Mitigations 

Risk 

Mitigation 

Poor quality AI-generated questions 

Human-in-the-loop review process 

Learner distrust in skipping recommendations 

Provide transparent scoring and result breakdown 

Lack of course content standardization 

Pilot with a subset of content types 

 

10. Timeline (High-Level) 

Design & Architecture: July 2025 

Prototype & AI Integration: August 2025 

Author Review Tools: August–September 2025 

User Testing & Feedback: September 2025 

MVP Release (proof of concept MVP): October 2025 

11. Open Questions 

What threshold determines if a course or module is skippable? 

Should we offer different quiz types depending on content complexity? 

What feedback do content providers need to feel confident in the AI-generated questions? 

 

 

System Architecture  

1. Purpose 

This document defines the modular system architecture for the Dynamic Quiz Creator MVP. It outlines the agents, services, and orchestrators needed to support AI-driven quiz generation, delivery, scoring, and learner profiling. 

 

2. Architectural Overview 

The system is composed of modular agents grouped into functional layers. Each layer performs a specialized role with clear handoffs to the next. 

Picture 

3. Layer-by-Layer Breakdown 

3.1 Content Ingestion Layer (Pluggable for V2) 

Agents: 

PDF Ingestor Agent 

Video Transcript Agent 

Orchestrator: 

Content Ingestion Orchestrator 

Detects content format 

Delegates to the correct agent 

Normalizes content to a unified schema (text + metadata) 

🟨 Status in MVP: Simulated via manual uploads or static content 

 

3.2 Quiz Generation Engine 

Agents: 

Multiple Choice Generator 

True/False Generator 

Fill-in-the-Blank Generator 

Short Answer Generator 

Orchestrator: 

Quiz Composition Orchestrator 

Defines question mix per course/module 

Coordinates type-specific agents 

Filters for clarity, relevance, diversity 

🟩 Status in MVP: Fully implemented 

 

3.3 Quiz Review Interface 

Functionality: 

Allow content providers to view/edit AI-generated questions 

Approve or regenerate specific items 

Preview learner experience 

🟩 Status in MVP: Required 

 

3.4 Quiz Delivery & Scoring 

Services: 

Quiz UI rendering 

Input capture and validation 

Scoring logic for auto-gradable questions 

Optional AI-assisted scoring for short answers 

🟩 Status in MVP: Required 

 

3.5 Results Analysis & Recommendations 

Engine: 

Aggregates scores by topic/module 

Applies rule-based logic to: 

Recommend full course skip 

Recommend module-level skip 

Generate feedback text 

🟩 Status in MVP: Required (basic logic) 

 

3.6 Learner Profile Service 

Stores: 

Quiz history 

Scores and recommendations 

Feedback summaries 

🟩 Status in MVP: Required 

 

4. Out-of-Scope (MVP) 

Admin analytics dashboards 

Full authentication integration 

Real-time adaptive quizzes 

Rich media ingestion (PDF, video, etc.) 

 

5. Optional V2+ Agents 

Course Difficulty Estimator Agent 

Learner Proficiency Estimator Agent 

Adaptive Quiz Generator Agent 

 

6. Design Principles 

Modular and pluggable agents 

Clear separation of responsibilities 

Extensible to support more content types and quiz formats in future versions 

 

7. Risks & Mitigations 

Risk 

Mitigation 

Inconsistent content formats 

Normalize content early in pipeline 

Low-quality AI output 

Human review layer in quiz creation 

Performance bottlenecks 

Asynchronous agent execution design 

 

 