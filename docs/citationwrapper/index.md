---
title: CitationWrapper
kind: class
longname: CitationWrapper
description: The CitationWrapper wraps a single citation in the Phyx document. Based on BibJSON (http://okfnlabs.org/bibjson/).
group: Wrappers
order: 8
---

# CitationWrapper

<SourceLink href="/source/wrappers/citationwrapper-js/#L8" label="CitationWrapper.js:8" />

The CitationWrapper wraps a single citation in the Phyx document. Based on BibJSON (http\://okfnlabs.org/bibjson/).

---

## Constructor

<Signature code="new CitationWrapper(citation): CitationWrapper" />

Construct a CitationWrapper.

---

## Instance Methods

<MemberHeading id="tostring" depth="3" name="toString" sig="toString()" />

<MemberMeta sourceHref="/source/wrappers/citationwrapper-js/#L56" sourceLabel="CitationWrapper.js:56" />

Returns a single string with the entire bibliographic citation.

## Static Methods

<MemberHeading id="normalize" depth="3" name="normalize" sig="normalize()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/citationwrapper-js/#L23" sourceLabel="CitationWrapper.js:23" />

Return a normalized form of a citation.

I'm not really sure how to normalize a citation, but the main thing we can do is delete any key that is equivalent to ''. We could interconvert between `name` and `firstname/lastname/middlename`, but that's not really equivalent, is it?

<MemberHeading id="getagentname" depth="3" name="getAgentName" sig="getAgentName()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/citationwrapper-js/#L40" sourceLabel="CitationWrapper.js:40" />

Helper method to return a single name for a given agent entry. The algorithm we use is:

- `name`, if one is present.
- Some combination of `lastname`, `firstname` and `middlename`, if present.
