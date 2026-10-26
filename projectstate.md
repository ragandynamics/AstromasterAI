# AstoMaestroAI --- Project State

**Document type:** Project state / product planning snapshot\
**Last updated:** 2026-10-13\
**Status:** Concept definition; requirements and implementation approach
not yet confirmed

## 1. Project overview

AstoMaestroAI is being explored as a Tamil-focused astrology experience
that combines traditional Tamil Jothidam concepts with practical,
personalised lifestyle guidance.

The product opportunity is to go beyond generic horoscope predictions
and help users reflect on current life themes and choose useful everyday
actions. Astrology should be presented as a traditional interpretive
framework, not as a scientifically established way to predict outcomes
or diagnose health, financial, or relationship issues.

## 2. Target users and needs

Potential users include Tamil-speaking and Tamil-heritage audiences,
including communities in Tamil Nadu, Singapore, Malaysia, and Sri Lanka.
Language, customs, religious practice, and astrology preferences will
vary, so these should be configurable rather than assumed.

Common user needs identified: - Jathagam / birth-chart interpretation -
Marriage compatibility (Thirumana Porutham) - Career, work, and business
guidance - Family and relationship reflection - Dasha Bhukti and
planetary transit explanations - Dosham and optional traditional
Pariharam guidance - Auspicious timing / Muhurtham - Money and
property-related reflection - Daily and yearly Rasi Palan - Personalised
explanations in Tamil and English

These are product hypotheses, not validated market research findings.

## 3. Proposed signature feature: Wheel of Life

### Goal

Create a personalised **Life Focus Wheel** that summarises astrological
themes across major life domains and turns those themes into practical,
optional daily or weekly suggestions.

### Proposed domains

A 12-domain model is under consideration: 1. Career and purpose 2. Money
and resources 3. Love and relationships 4. Family and home 5. Health and
vitality 6. Mind and emotions 7. Learning and intelligence 8.
Spirituality 9. Social life 10. Creativity 11. Confidence and personal
growth 12. Rest and recreation

### Domain content

Each domain should be able to show: - **Astrological theme:** a
transparent interpretation based on the selected astrology method and
relevant chart factors. - **Current focus:** a theme or reflection
prompt for the current period. - **Practical action:** one or two useful
actions for today or the week. - **Explanation:** why the system
suggested the theme or action. - **Uncertainty/context:** a clear note
that astrological interpretations are traditional beliefs, not
guaranteed outcomes.

### Scoring and visualisation

The chart should not imply that a user's real-life success, health,
marriage, or finances can be objectively measured from planetary
positions.

Preferred terminology: - "Life Focus Wheel" - "Current themes" - "Focus
areas" - "Traditional astrological interpretation"

Potential status approaches: - Supportive / Balanced / Needs Attention -
High / Medium / Low priority, with explanations - Astrological
intensity, only if the underlying calculation method is defined and
clearly distinguished from real-world outcomes

A numerical 0--100 score should not be presented as an objective
life-quality or outcome prediction. If scores are used, document exactly
what they measure and how they are calculated.

## 4. Lifestyle recommendation modules

### Food

Potential functionality: - Culturally relevant meal ideas, including
South Indian options - Vegetarian, vegan, and non-vegetarian
preferences - Allergy and dietary restriction handling - Practical meal
and hydration reminders - Optional traditional symbolic food
associations for specific days or observances

Safety requirements: - Do not recommend food that conflicts with known
allergies or dietary restrictions. - Do not claim planetary positions
medically require a particular diet. - Do not make medical treatment or
disease-prevention claims.

### Clothing and colours

Potential functionality: - Optional colour-of-the-day suggestions -
Traditional colour symbolism linked to weekdays or the user's selected
astrology tradition - Outfit ideas based on occasion, climate, comfort,
and personal style - Traditional attire suggestions for ceremonies or
temple visits, where requested

Safety and trust requirements: - Frame colour associations as cultural
or spiritual symbolism, not guaranteed luck or success. - Respect user
preferences and avoid assuming gender, religion, or dress practices.

### Activities and daily actions

Potential functionality: - Work and study focus suggestions - Walking,
movement, stretching, and rest reminders - Family and relationship
activities - Meditation, prayer, or journaling, when desired - Planning,
decluttering, and creative activities - Weekly goal setting and
reflection

Recommendations should be realistic, low-risk, and appropriate to the
user's schedule and circumstances.

### Optional spiritual practices

Potential functionality: - Mantra, prayer, or reflection prompts -
Traditional observances - Charitable acts and acts of kindness -
Optional temple-related suggestions

Requirements: - Keep practices optional and respectful. - Avoid
fear-based messaging. - Do not imply that paid rituals are necessary to
prevent misfortune or guarantee results.

## 5. Personalisation model

Three information layers are proposed:

1.  **Birth chart:** Rasi, Nakshatra, Lagna, planetary placements, and
    relevant house interpretations.
2.  **Current astrological period:** Dasha Bhukti, planetary transits,
    and applicable Panchangam factors, depending on the chosen
    calculation method.
3.  **Real-world preferences and context:** language, dietary
    preferences, allergies, budget, climate, schedule, lifestyle goals,
    and optional spiritual preferences.

Core principle: astrology may shape the symbolic interpretation, but
practical circumstances and safety constraints must determine whether a
recommendation is appropriate.

The system should explain why each recommendation was generated rather
than returning unexplained AI-generated advice.

## 6. Proposed daily experience

A daily view could include: - Today's astrological theme - One-paragraph
explanation - Life Focus Wheel overview - Food idea, respecting dietary
preferences - Optional colour or clothing suggestion - One practical
activity - Relationship or reflection prompt - Optional traditional
spiritual guidance - Links to the relevant Rasi, Nakshatra, Dasha
Bhukti, or transit interpretation

Until a user's chart is actually calculated, examples must be labelled
illustrative and must not be represented as personalised predictions.

## 7. Broader recommended feature roadmap

### MVP --- test the core experience

-   Basic Jathagam onboarding or a clear sample mode
-   Life Focus Wheel with explainable domain themes
-   Daily practical activity suggestions
-   Optional colour guidance
-   Tamil and English interface/content foundations
-   User feedback on relevance and usefulness

### Phase 2 --- astrological personalisation

-   Birth-chart calculations
-   Transit and Dasha Bhukti integration
-   Explanations of the selected Tamil astrology method
-   Personalised daily and weekly readings
-   Marriage compatibility as a separate feature, if prioritised

### Phase 3 --- lifestyle personalisation

-   Food preferences and meal ideas
-   Wardrobe and occasion recommendations
-   User schedules and goal preferences
-   Optional spiritual-practice module

### Phase 4 --- retention and refinement

-   Weekly/monthly reports
-   User-controlled life-domain priorities
-   Saved suggestions and completion feedback
-   Trend views that reflect user self-assessments, not astrological
    claims of objective life quality
-   Improved localisation for different Tamil communities

This roadmap is provisional and should be revised after user research
and feasibility review.

## 8. Product principles and guardrails

-   **Transparent:** explain which chart factors and rules informed each
    interpretation.
-   **Culturally respectful:** let users choose language, tradition, and
    level of spiritual content.
-   **Non-deterministic:** avoid claims that planetary positions
    guarantee events or outcomes.
-   **Practical:** prioritise useful, low-risk actions.
-   **Safe:** dietary, health, financial, and relationship guidance must
    not replace qualified professional advice.
-   **Non-exploitative:** no fear-based predictions or pressure to buy
    remedies.
-   **Privacy-conscious:** collect only necessary birth and preference
    data; explain why it is needed and how it is handled.
-   **User-led:** allow users to hide or customise spiritual and
    lifestyle recommendation categories.

## 9. Success metrics to validate

Potential metrics: - Onboarding completion rate - Percentage of users
who view the Life Focus Wheel - Daily and weekly return rate -
Recommendation save/usefulness feedback - Percentage of users who find
explanations clear - Tamil versus English engagement - Opt-in rates for
lifestyle categories - Reports of irrelevant, unsafe, or culturally
mismatched suggestions

Do not optimise solely for time spent or frequency of astrological
predictions. User trust and usefulness should be central.

## 10. Open decisions

The following decisions are not yet confirmed:

1.  **Wheel calculation approach**
    -   Pure astrology: derive themes from chart factors and Dasha
        Bhukti.
    -   Combined: astrology plus a short user self-assessment.
    -   Reflection-first: measure user-reported life satisfaction, with
        astrology as optional interpretation.
2.  **Visual approach**
    -   Traditional circular wheel
    -   Modern dashboard cards
    -   Both: wheel overview plus practical recommendation cards
3.  **Astrology methodology**
    -   Define the Tamil/Vedic calculation conventions to support.
    -   Decide how to handle differing schools or interpretations.
    -   Identify and validate the ephemeris, Panchangam, and
        chart-calculation sources.
4.  **Languages and launch market**
    -   Confirm Tamil script, English, and any additional language
        support.
    -   Select initial user segment and market for testing.
5.  **Data and privacy**
    -   Decide required birth details and timezone handling.
    -   Define consent, retention, deletion, and data-access policies.
6.  **Commercial model**
    -   Decide which features are free, premium, or subscription-based.
    -   Validate willingness to pay before committing to a monetisation
        design.
7.  **Implementation**
    -   Choose platform, technical stack, chart calculation engine, and
        AI/content architecture.
    -   No technical stack or implementation status has been confirmed
        in the discussion so far.

## 11. Immediate next steps

1.  Choose the Wheel of Life calculation approach and visual style.
2.  Define the astrological methodology and how domain interpretations
    are derived.
3.  Create a sample user journey with clearly labelled example data.
4.  Prototype the wheel and daily recommendation cards.
5.  Test the prototype with a small, diverse group of Tamil users.
6.  Review dietary, health, financial, privacy, and spiritual-content
    safeguards.
7.  Prioritise the MVP based on user feedback and implementation
    feasibility.

## 12. Current status summary

**Current stage:** Product concept and feature exploration.

**Most promising differentiator:** A Tamil-first, personalised astrology
experience that connects traditional interpretations with practical
daily lifestyle suggestions.

**Next decision needed:** Confirm whether the Life Focus Wheel should be
astrology-led, combined with self-assessment, or reflection-first; then
choose a circular wheel, dashboard, or combined presentation.

**Not yet completed or confirmed:** User research, validated demand,
astrology calculation specifications, UI prototype, technical
architecture, implementation, testing, pricing, and launch plan.
