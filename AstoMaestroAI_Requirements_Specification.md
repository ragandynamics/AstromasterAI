# AstoMaestroAI — Requirements Specification

**Document ID:** ASTO-REQ-001  
**Version:** 0.1 — Draft for review  
**Date:** 13 October 2026  
**Status:** Proposed requirements; not yet validated or approved

## 1. Purpose

This document defines initial product and system requirements for AstoMaestroAI, a Tamil-focused astrology and lifestyle guidance platform. It is intended to align product, design, engineering, content, and testing work before implementation.

This is a first-pass specification based on concept discussions. It is not a claim that market demand, technical feasibility, astrology calculations, or regulatory compliance have already been validated.

## 2. Product vision

Help users explore traditional Tamil astrology interpretations and turn them into practical, optional everyday reflections and lifestyle suggestions. The product should be culturally respectful, transparent about the interpretive nature of astrology, personalised where users consent, and safe in its recommendations.

## 3. Goals and success criteria

### 3.1 Product goals
- Provide understandable, personalised Jathagam-based interpretations.
- Make the Wheel of Life a signature summary of current life themes.
- Offer practical daily and weekly suggestions for activities, food, clothing/colours, reflection, and optional spiritual practices.
- Support Tamil and English content, with localisation decisions validated with users.
- Explain why each suggestion appears and allow users to adjust preferences.

### 3.2 Initial success metrics
- Onboarding completion rate.
- Percentage of users who view the Wheel of Life.
- Daily and weekly return rate.
- Recommendation usefulness ratings and save/use actions.
- Clarity ratings for astrological explanations.
- Tamil/English engagement and preference opt-in rates.
- Rate of reported irrelevant, culturally mismatched, or unsafe suggestions.

Targets should be set after baseline testing; do not invent targets before collecting baseline data.

## 4. Scope

### 4.1 In scope for planning
- User onboarding and birth-data collection.
- Jathagam profile and chart interpretation.
- Wheel of Life with configurable life domains.
- Dasha Bhukti and transit interpretation, subject to a selected and validated calculation method.
- Daily/weekly lifestyle recommendations.
- Tamil and English experience.
- User preferences, explanations, feedback, and privacy controls.
- Content safety and quality controls.

### 4.2 Proposed MVP
1. Profile setup and consent.
2. Birth details and timezone handling.
3. Basic chart summary or clearly labelled sample mode.
4. Eight to twelve life-domain themes, with an initial 12-domain model.
5. Daily theme and one or two practical actions.
6. Basic colour suggestion, explicitly optional and symbolic.
7. Tamil/English content foundation.
8. Explanation of why a theme or suggestion was generated.
9. User feedback and preference controls.
10. Privacy, account, and data deletion flows appropriate to the selected platform.

### 4.3 Later phases
- Full Dasha Bhukti and transit reports.
- Marriage compatibility / Thirumana Porutham.
- Food and meal ideas based on user preferences.
- Wardrobe and occasion recommendations.
- Muhurtham finder.
- Optional spiritual guidance.
- Weekly/monthly reports and saved plans.
- Subscription and premium features, after willingness-to-pay validation.

### 4.4 Out of scope for initial release
- Medical diagnosis or treatment.
- Guaranteed predictions of marriage, fertility, health, wealth, career, or other outcomes.
- Automated investment, legal, or medical decisions.
- Fear-based warnings or paid remedies represented as necessary to prevent misfortune.
- Unvalidated claims that astrological calculations objectively measure real-world life quality.

## 5. Users and personas

### Persona A: Tamil astrology seeker
Wants to understand Rasi, Nakshatra, Jathagam, Dasha Bhukti, and current traditional interpretations in accessible language.

### Persona B: Practical lifestyle user
Wants short daily prompts and helpful activities, with astrology as an optional framing.

### Persona C: Family decision-maker
May explore compatibility, auspicious timing, or family-related interpretations. The platform must avoid coercive or deterministic messaging.

### Persona D: Bilingual Tamil/English user
Wants terminology and explanations in a preferred language, potentially mixing familiar Tamil astrology terms with plain-language explanations.

These personas are hypotheses and should be tested with users.

## 6. Functional requirements

Priority definitions: **Must** = needed for MVP safety or core use; **Should** = important but can follow the first usable version; **Could** = optional or later-phase functionality.

### FR-001 — Language preference
**Priority:** Must  
The system shall let users choose a supported language, initially proposed as Tamil and English.  
**Acceptance criteria:**
- User can select a language during onboarding or in settings.
- Primary navigation and supported content follow the selected language.
- If a translation is unavailable, the system clearly identifies the fallback language rather than silently mixing content.

### FR-002 — Profile and consent
**Priority:** Must  
The system shall explain why profile and birth details are requested and obtain appropriate consent before processing them.  
**Acceptance criteria:**
- Required and optional fields are clearly distinguished.
- Users can review and edit profile data.
- Privacy notice and data-handling information are accessible during onboarding.

### FR-003 — Birth details
**Priority:** Must for personalised chart mode  
The system shall collect the birth date, birth time (including an “unknown” option), and birthplace or an equivalent location/timezone input required by the selected chart engine.  
**Acceptance criteria:**
- Local time and timezone are handled explicitly.
- Unknown or approximate birth time is represented as uncertainty; the UI does not imply false precision.
- The user can correct entered details.
- The chart engine's required inputs and limits are documented.

### FR-004 — Astrology methodology and chart calculation
**Priority:** Must before personalised predictions launch  
The system shall use a documented, testable astrology calculation method selected by the product owner.  
**Acceptance criteria:**
- Supported conventions (e.g., zodiac/ayanamsa, house system, ephemeris, timezone and location handling) are documented.
- Calculation source and version are traceable.
- Known test charts have expected outputs and regression tests.
- Missing inputs and calculation failures are surfaced clearly.
- Interpretations identify the method or tradition used where relevant.

### FR-005 — Jathagam profile
**Priority:** Should for MVP; Must before dependent personalised features  
The system shall present supported chart elements such as Rasi, Nakshatra, Lagna, planetary placements, and relevant house interpretations when calculable.  
**Acceptance criteria:**
- Each displayed element has a clear label and explanation.
- Unknown birth time limitations are shown.
- No element is fabricated when the calculation cannot be completed.

### FR-006 — Wheel of Life overview
**Priority:** Must  
The system shall display a Wheel of Life / Life Focus Wheel summarising interpretations across configured life domains.  
**Initial proposed domains:**
1. Career and purpose
2. Money and resources
3. Love and relationships
4. Family and home
5. Health and vitality
6. Mind and emotions
7. Learning and intelligence
8. Spirituality
9. Social life
10. Creativity
11. Confidence and personal growth
12. Rest and recreation

**Acceptance criteria:**
- User can open the wheel and inspect each domain.
- Each domain displays a theme, explanation, and suggested reflection or action where available.
- Domains with insufficient chart data are marked unavailable or general, not assigned invented values.
- The UI makes clear that the wheel is an astrological interpretation, not an objective measurement of the user's life.
- The visual remains readable on supported mobile and desktop sizes.

### FR-007 — Domain interpretation and explainability
**Priority:** Must  
The system shall provide a plain-language explanation of the factors used to generate each astrological theme.  
**Acceptance criteria:**
- Each personalised interpretation is traceable to documented chart factors and content rules.
- The system distinguishes calculated chart facts from interpretive statements and general lifestyle suggestions.
- Generic fallback content is labelled as general guidance.
- Contradictory or low-confidence interpretations are handled according to documented rules.

### FR-008 — Scoring or status labels
**Priority:** Should  
If the product uses domain scores or labels, it shall define their meaning and avoid presenting them as objective predictions of life outcomes.  
**Acceptance criteria:**
- A score has a documented formula and meaning.
- Scores are not described as measured health, wealth, relationship quality, or future success.
- If the calculation is not sufficiently defined, use non-numeric themes or focus labels instead.
- Users can access an explanation of any displayed status.

### FR-009 — Daily guidance
**Priority:** Must  
The system shall present a concise daily theme and one or two practical actions, with an optional deeper explanation.  
**Acceptance criteria:**
- Guidance is actionable and non-deterministic.
- The date and relevant timezone are clear.
- Users can dismiss, save, or rate suggestions where supported.
- The system does not claim guaranteed outcomes.

### FR-010 — Activity recommendations
**Priority:** Must  
The system shall recommend low-risk activities such as planning, study, walking, reflection, rest, or relationship-building, based on configured content rules and user context.  
**Acceptance criteria:**
- Suggestions are realistic and optional.
- Suggestions account for user-provided schedule or accessibility constraints when available.
- High-risk or specialist advice is excluded or appropriately qualified.

### FR-011 — Food and meal suggestions
**Priority:** Should; proposed Phase 3 unless needed for MVP validation  
The system may suggest meal ideas based on user preferences and practical context.  
**Acceptance criteria:**
- Users can specify dietary preference and allergies/restrictions where this feature is enabled.
- Suggestions respect known restrictions.
- Astrology is not presented as a medical reason to eat or avoid a food.
- The feature avoids disease-treatment, cure, or prevention claims.
- Users can hide food recommendations.

### FR-012 — Clothing and colour recommendations
**Priority:** Could for MVP; Should for lifestyle phase  
The system may offer optional colour symbolism and outfit suggestions based on the selected tradition, occasion, climate, and user preference.  
**Acceptance criteria:**
- Symbolic associations are labelled as cultural/traditional interpretations.
- Suggestions do not promise luck, success, or protection.
- Users can disable the feature.
- The system does not assume gender, religion, or dress practice.

### FR-013 — Optional spiritual practices
**Priority:** Could  
The system may offer optional prayers, mantras, meditation, charity, or traditional observances when users opt in.  
**Acceptance criteria:**
- Users can opt out at any time.
- Practices are respectful and non-coercive.
- No paid ritual is presented as necessary to prevent harm or guarantee an outcome.
- Religious and cultural preferences are not inferred without user input.

### FR-014 — Preferences and personalisation
**Priority:** Must  
The system shall let users manage relevant preferences, including language, recommendation categories, dietary needs when applicable, and optional spiritual content.  
**Acceptance criteria:**
- Preferences can be changed after onboarding.
- Hidden categories do not appear in routine recommendations.
- The system uses only necessary data for each feature.

### FR-015 — Feedback
**Priority:** Should  
The system shall collect optional feedback on relevance, clarity, and usefulness.  
**Acceptance criteria:**
- Feedback can be submitted with minimal effort.
- Feedback does not require users to disclose sensitive personal details.
- Feedback is available to product evaluation under an approved privacy policy.

### FR-016 — Reports and history
**Priority:** Could / later phase  
The system may provide weekly or monthly summaries and saved recommendations.  
**Acceptance criteria:**
- Reports clearly identify their time period and calculation basis.
- Historical trends based on self-assessment are distinguished from astrology-derived themes.
- Users can delete saved history according to the data policy.

### FR-017 — Compatibility and Muhurtham
**Priority:** Later phase  
The system may provide marriage compatibility and auspicious timing tools after methodology and demand are validated.  
**Acceptance criteria:**
- Compatibility is presented as a traditional interpretation, not a definitive judgment of relationship success.
- Results avoid coercive recommendations about marriage.
- Muhurtham outputs show the location, timezone, calculation method, and assumptions used.
- Missing or uncertain inputs are disclosed.

## 7. Non-functional requirements

### NFR-001 — Usability
The primary daily experience should be understandable at a glance, with plain-language explanations and deeper details available on demand.

### NFR-002 — Accessibility
The interface should support readable typography, sufficient contrast, keyboard/screen-reader considerations appropriate to the selected platform, and responsive layouts.

### NFR-003 — Performance
Set measurable response-time targets after the platform and architecture are selected. Chart calculations and generated content should expose loading, success, and failure states.

### NFR-004 — Reliability
Chart calculations must be deterministic for identical inputs and calculation versions. Failures must not silently produce fabricated placements or recommendations.

### NFR-005 — Security and privacy
- Collect only data required for the enabled features.
- Protect birth details, location data, preferences, and account data in transit and at rest according to the chosen platform's security standard.
- Define access controls, retention, deletion, backup, and incident response.
- Do not use sensitive profile data for unrelated purposes without appropriate consent.
- Provide a clear privacy notice and account/data deletion process.

### NFR-006 — Explainability and auditability
The system should record the relevant calculation version, rules, and content version needed to investigate a reported result, while avoiding unnecessary storage of sensitive data.

### NFR-007 — Localisation
Tamil content should be reviewed for script quality, terminology, cultural nuance, and readability by fluent reviewers. English content should explain Tamil terms where helpful.

### NFR-008 — Content safety
The system must avoid deterministic or fear-based claims and must not substitute for qualified medical, mental-health, financial, legal, or other professional advice.

### NFR-009 — Maintainability
Astrology rules, translations, and recommendation content should be versioned and testable independently from the UI where feasible.

## 8. Data requirements

Potential data categories:
- Account identifier and authentication data, if accounts are supported
- Birth date, birth time, birthplace/location, and timezone
- Selected astrology conventions and calculated chart output
- Language and lifestyle preferences
- Optional dietary restrictions and allergies, only if food features are enabled
- Recommendation history and user feedback, if enabled
- Consent records and privacy-related settings

For each field, implementation planning must define whether it is required, purpose, retention, access, deletion, and whether it is shared with any third party. Avoid collecting sensitive information that is not needed.

## 9. User journeys

### Journey A — First-time personalised setup
1. User chooses language.
2. User sees a concise explanation of the service and its limitations.
3. User reviews privacy information and provides required consent.
4. User enters birth details, including unknown/approximate options where supported.
5. System validates inputs and explains any limitations.
6. User sees a chart summary and/or Life Focus Wheel.
7. User can inspect the explanation behind each domain.

### Journey B — Daily guidance
1. User opens the daily view.
2. System shows the date, daily theme, and source/context of the interpretation.
3. User sees optional activity, colour, or other enabled lifestyle suggestions.
4. User can save, dismiss, rate, or customise the suggestions.

### Journey C — Lifestyle preferences
1. User opens settings.
2. User chooses recommendation categories and relevant preferences.
3. System updates future recommendations.
4. User can revise preferences or disable categories at any time.

### Journey D — Uncertain birth information
1. User indicates that birth time is unknown or approximate.
2. System explains which chart elements may be less reliable or unavailable.
3. System avoids presenting unsupported precision.
4. User can continue with the available level of interpretation.

## 10. Acceptance and release criteria

A release candidate should not be approved until:
- Requirements marked Must are implemented or explicitly waived by the product owner.
- Chart methodology and test cases are documented for personalised astrology features.
- Critical user journeys pass functional and usability testing.
- Tamil and English content receives appropriate review.
- Privacy and deletion flows are tested.
- Food recommendations, if enabled, respect known allergies and restrictions.
- All astrological interpretations are distinguishable from general advice.
- No critical or high-severity safety issues remain unresolved.
- Known limitations are visible to users.

## 11. Risks and mitigations

| Risk | Mitigation |
|---|---|
| Users interpret the wheel as an objective life-quality score | Prefer themes and focus labels; explain score meaning and limitations |
| Astrology traditions produce differing interpretations | Select, document, and version the supported method |
| Birth-time or timezone errors distort charts | Validate inputs, record timezone assumptions, expose uncertainty |
| Generic AI output conflicts with chart calculations | Separate calculation outputs from generation; constrain generation to structured inputs |
| Dietary suggestions conflict with restrictions | Make restriction handling explicit and test it; allow users to disable food guidance |
| Cultural or religious assumptions alienate users | Make spiritual content optional and preferences user-controlled |
| Fear-based content undermines trust | Prohibit coercive warnings and claims that paid remedies are required |
| Data collection creates privacy risk | Minimise collection, document purpose and retention, provide deletion controls |
| Feature scope grows too quickly | Validate the MVP with users before building later-phase modules |

## 12. Open decisions

The following require product-owner decisions before detailed design or implementation:

1. Wheel model: astrology-led, astrology plus self-assessment, or reflection-first.
2. Visual model: circular wheel, dashboard cards, or both.
3. Supported Tamil/Vedic calculation conventions, ephemeris, ayanamsa, house approach, and Panchangam source.
4. Initial launch market, supported languages, and localisation requirements.
5. Platform and technical architecture.
6. Required birth inputs and behaviour when time/place is unknown.
7. Which lifestyle modules are included in MVP.
8. Account model, privacy policy, retention, and deletion requirements.
9. Pricing and premium-feature boundaries.
10. User research plan and measurable MVP targets.

## 13. Proposed implementation sequence

1. Validate user needs and the initial personas.
2. Decide wheel model, domains, labels, and visual approach.
3. Specify and validate astrology calculations with known test cases.
4. Define content rules and explanation templates.
5. Prototype onboarding, wheel, and daily guidance.
6. Conduct usability and cultural review with a diverse group of Tamil users.
7. Implement the MVP and safety/privacy controls.
8. Run functional, accessibility, localisation, and safety testing.
9. Launch a limited pilot, collect feedback, and prioritise improvements.

## 14. Glossary

- **Jathagam:** Birth horoscope/chart.
- **Rasi:** Zodiac sign or sign-based chart reference in the relevant tradition.
- **Nakshatra:** Lunar mansion.
- **Lagna:** Ascendant.
- **Dasha Bhukti:** Major and sub-periods used in Vedic/Tamil astrology systems.
- **Panchangam:** Traditional almanac/calendar factors used for timing and observances.
- **Muhurtham:** Traditionally auspicious timing for an event.
- **Pariharam:** Traditional remedial or spiritual practice.
- **Life Focus Wheel:** A visual summary of life domains and their current themes in this product; not an objective measure of real-world outcomes.

## 15. Approval

| Role | Name | Status | Date |
|---|---|---|---|
| Product owner | TBD | Pending review | TBD |
| Engineering lead | TBD | Pending review | TBD |
| Design/content lead | TBD | Pending review | TBD |
| Privacy/safety reviewer | TBD | Pending review | TBD |

---

**Document note:** This specification is a draft derived from product concept discussions. All requirements, priorities, methods, and release plans must be reviewed and approved before implementation.
