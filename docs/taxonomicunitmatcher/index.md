---
title: TaxonomicUnitMatcher
kind: class
longname: TaxonomicUnitMatcher
description: "The TaxonomicUnitMatcher matches pairs of taxonomic units and provides a consistent report on: Which taxonomic units have matched, and Why the match occurred. In Model 2.0, we start by using direct matching in OWL, so this should no longer be needed. However, I'll leave this around to provide matching in the Curation Tool UI and in case it's needed again later."
group: Matchers
---

# TaxonomicUnitMatcher

<SourceLink href="/source/matchers/taxonomicunitmatcher-js/#L16" label="TaxonomicUnitMatcher.js:16" />

The TaxonomicUnitMatcher matches pairs of taxonomic units and provides a consistent report on:

- Which taxonomic units have matched, and
- Why the match occurred.

In Model 2.0, we start by using direct matching in OWL, so this should no longer be needed. However, I'll leave this around to provide matching in the Curation Tool UI and in case it's needed again later.

---

## Constructor

<Signature code="new TaxonomicUnitMatcher(tunit1, tunit2): TaxonomicUnitMatcher" />

Create a Taxonomic Unit Matcher to match two taxonomic units. Matching will occur immediately, so when this method returns, you can check tuMatch.matched and tuMatch.matchReason to determine if the two TUs matched and why.

---

## Instance Methods

<MemberHeading id="asjsonld" depth="3" name="asJSONLD" sig="asJSONLD()" />

<MemberMeta sourceHref="/source/matchers/taxonomicunitmatcher-js/#L36" sourceLabel="TaxonomicUnitMatcher.js:36" />

Return this TUMatch as a JSON object for insertion into the PHYX file.

<MemberHeading id="match" depth="3" name="match" sig="match()" />

<MemberMeta sourceHref="/source/matchers/taxonomicunitmatcher-js/#L50" sourceLabel="TaxonomicUnitMatcher.js:50" />

Try to match the two taxonomic units using a number of matching methods.

<MemberHeading id="matchbynamecomplete" depth="3" name="matchByNameComplete" sig="matchByNameComplete()" />

<MemberMeta sourceHref="/source/matchers/taxonomicunitmatcher-js/#L64" sourceLabel="TaxonomicUnitMatcher.js:64" />

Try to match by nameComplete, and return true if it could be matched.

<MemberHeading id="matchbyexternalreferences" depth="3" name="matchByExternalReferences" sig="matchByExternalReferences()" />

<MemberMeta sourceHref="/source/matchers/taxonomicunitmatcher-js/#L84" sourceLabel="TaxonomicUnitMatcher.js:84" />

Match by external references.

<MemberHeading id="matchbyoccurrenceid" depth="3" name="matchByOccurrenceID" sig="matchByOccurrenceID()" />

<MemberMeta sourceHref="/source/matchers/taxonomicunitmatcher-js/#L108" sourceLabel="TaxonomicUnitMatcher.js:108" />

Match by occurrence ID
