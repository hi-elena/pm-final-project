# Spotlight Curated Rail, Simplified PRD (StreamLine)

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** A passionate film enthusiast who values cinematic quality, originality and discovering hidden gems beyond mainstream recommendations.

## 1. The Big Picture
- **Vision:** To eliminate the frustration of overwhelming choice and impersonal recommendations by making StreamLine a trusted destination for effortless, human-curated discovery of exceptional cinema.
- **Press release:** Introducing StreamLine Spotlight — Less scrolling, more discovering.

Great cinema deserves to be discovered, not buried beneath endless recommendations. StreamLine Spotlight introduces a hand-picked collection of exceptional films, hidden gems and original storytelling, curated by people who share your passion for cinema. No more repetitive franchise recommendations or endless scrolling in search of something worth watching.

By putting human expertise at the heart of discovery, Spotlight transforms an overwhelming library into an inspiring, trusted destination for film lovers. Spend less time deciding what to watch and more time enjoying cinema that is worth discovering.
- **Success metric:** Curated Content Discovery-to-Play Conversion Rate
- **Guardrail:** Average Weekly Viewing Sessions per Power User

## 2. The Details
### User stories
- - As a film enthusiast, I want to easily find a dedicated curated collection on the homepage so that I can discover exceptional cinema without endless scrolling.
- - As a film enthusiast, I want to know that films have been selected by human curators so that I can trust the recommendations.
- - As a film enthusiast, I want to discover original and lesser-known films so that I am not limited to repetitive mainstream recommendations.
- - As a film enthusiast, I want to access film details directly from the curated rail so that I can make an informed viewing decision.
- - As a film enthusiast, I want to start watching my chosen film seamlessly so that I can spend more time watching and less time searching.
- - As a film enthusiast, I want to retain access to my existing discovery options so that I can continue enjoying StreamLine without disrupting my viewing habits.
- - As a content curator, I want to manually select, order and update films in the Spotlight rail so that I can maintain a relevant, high-quality collection independent of algorithmic recommendations.
### Screens to build
- 1. Entry point — Homepage	Existing homepage featuring a prominently positioned Spotlight Curated Rail, clearly labelled as human-curated, with hand-picked film titles and artwork.	Easily discovers a trusted alternative to algorithmic recommendations.
- 2. Feature core — Film Details	Selected film's artwork, synopsis, genre, runtime and Play button, reusing the existing title details screen.	Confidently decides whether the film is worth watching.
- 3. Success/confirmation — Playback	Existing video player successfully starts the selected film.	Watches a film discovered through Spotlight, completing the discovery-to-play journey.
### Functional requirements
- ID	Requirement
- FR-01	The system must display a dedicated Spotlight Curated Rail on the existing homepage.
- FR-02	The system must allow authorised content curators to manually select, order, update and remove films independently of the recommendation algorithm.
- FR-03	The rail must display a visible label identifying its content as human-curated.
- FR-04	Every film displayed in the rail must include its title and artwork.
- FR-05	Selecting a film must open its existing title details screen, from which the user can initiate playback.
- FR-06	The rail must only display films available to watch within the user's region and subscription entitlement.
- FR-07	The system must record rail impressions, title selections and successful playback starts, linking these events within the same session to measure Discovery-to-Play Conversion Rate.
- FR-08	The introduction of the Spotlight rail must not remove or disable any existing homepage discovery functionality.
### Smart behaviors (Situation → Outcome)
- - If a user opens the homepage, then display the latest published human-curated Spotlight collection.
- - If a curator updates the collection, then display the revised selection in the curator-defined order.
- - If a film is unavailable in the user's region or subscription, then exclude it from the rail.
- - If a user selects a film from Spotlight, then open its existing title details screen.
- - If a user successfully starts watching a film discovered through Spotlight within the same session, then record a discovery-to-play conversion.
- - If playback fails, then use the existing playback error-handling mechanism and do not record a successful conversion.
- - If no eligible curated titles are available, then hide the Spotlight rail rather than display an empty collection.
- - If the Spotlight rail fails to load, then allow the remaining homepage content to load and function normally.
### Technical constraints
- No external APIs: Use static, mock film data for the curated collection.
- No database: Store curated titles in a local JSON file or hardcoded data array.
- No backend development: Implement the prototype entirely on the frontend.
- No complex state management: Use React useState only; no Redux or external state management libraries.
- No AI or recommendation engine: Display manually selected films in a predefined editorial order.
- No content management system: Simulate editorial curation through a predefined dataset.
- No authentication or subscription management: Assume the user is already authenticated and eligible to watch the displayed content.
- No video streaming infrastructure: Simulate successful playback through a mock player.
- No live analytics integration: Simulate discovery-to-play events locally.
- No redesign of existing platform functionality: Limit development to the three defined screens and reuse existing UI patterns.

## 3. The Logistics
### Features out
- AI-generated recommendations and explanations.
- Personalised Spotlight rails and queues.
- Mood-based onboarding and filtering.
- Curator profiles and following functionality.
- Email digests and notifications.
- Advanced search and filtering.
- Homepage or recommendation engine redesign.
- Exclusive content acquisition or film restoration.
### Edge cases & safety guard
- Unhappy path	Expected behaviour
- No curated films available	Hide the Spotlight rail without disrupting the homepage.
- Missing film artwork	Display a standard placeholder with the film title.
- Film becomes unavailable	Exclude it from the curated collection.
- Spotlight fails to load	Keep the remaining homepage functional.
- Playback fails	Display an appropriate error message and allow the user to retry.
- User abandons discovery before playback	Do not record a successful conversion.
- User navigates back from film details	Return to the previous browsing position.
### Decision log
- Use a single, manually curated rail instead of personalised collections.	Directly addresses Marcus's core frustration while avoiding algorithmic and backend complexity.	Limited personal relevance in the initial release.
- Reuse existing homepage, film details and playback patterns instead of building a standalone Spotlight experience.	Protects the three-week sprint capacity and minimises disruption to existing viewing habits.	Less visual differentiation and editorial storytelling.
### Evals
- 100% accuracy
- Time-on-task: 60 seconds or less
- 100% of safety tests pass; zero critical violations

## MoSCoW scope
- **Must:** Dedicated Spotlight rail on the homepage; Ability to manually select and order titles; Clear identification of the rail as human-curated; Display existing title artwork and film names; Ability to select a title and access existing playback flow; Display only titles available to the user; Track rail impressions, title selections and playback starts; Preserve existing homepage discovery functionality
- **Should:** Short, human-written curator notes; Scheduled collection refreshes; Themed collection titles and descriptions; Dedicated editorial management interface
- **Could:** Hidden Gem badges; Named curator attribution; Multiple themed curated rails; Ability to explore previous curated collections; Feedback on curated selections
- **Won't (now):** AI-generated recommendations or explanations; Personalised Spotlight rails; Mood-based onboarding or filtering; Curator profiles and following functionality; Spotlight email digests or notifications

---
**Builder hook:** Build a working prototype based on this PRD. Use the User Story as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity.
