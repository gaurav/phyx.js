---
title: TaxonomicUnitWrapper
kind: class
longname: TaxonomicUnitWrapper
description: "The TaxonomicUnitWrapper wraps taxonomic units, whether on a node or being used as a specifier on a phyloreference. Every taxonomic unit can additionally be wrapped by more specific classes, such as {@link TaxonConceptWrapper} or {@link SpecimenWrapper}. We can determine which type it is based on its '@type' and whether it includes: TaxonomicUnitWrapper.TYPE_TAXON_CONCEPT =&gt; {@link TaxonConceptWrapper} TaxonomicUnitWrapper.TYPE_SPECIMEN =&gt; {@link SpecimenWrapper} TaxonomicUnitWrapper.TYPE_APOMORPHY =&gt; reserved for future use TaxonomicUnitWrapper.TYPE_PHYLOREF =&gt; reserved for future use It also contains static methods for extracting taxonomic units from arbitrary strings, such as phylogeny labels. Every taxonomic unit SHOULD have an rdfs:label and MAY include a dcterm:description to describe it in human-readable terms. It MUST include a '@type' that specifies what type of taxonomic unit it is. Taxonomic units may be specified with only an '@id' or a set of '@id's, which indicate external references."
group: Wrappers
---

# TaxonomicUnitWrapper

<SourceLink href="/source/wrappers/taxonomicunitwrapper-js/#L39" label="TaxonomicUnitWrapper.js:39" />

The TaxonomicUnitWrapper wraps taxonomic units, whether on a node or being used as a specifier on a phyloreference. Every taxonomic unit can additionally be wrapped by more specific classes, such as [TaxonConceptWrapper](/taxonconceptwrapper) or [SpecimenWrapper](/specimenwrapper). We can determine which type it is based on its '@type' and whether it includes:

- TaxonomicUnitWrapper.TYPE\_TAXON\_CONCEPT => [TaxonConceptWrapper](/taxonconceptwrapper)
- TaxonomicUnitWrapper.TYPE\_SPECIMEN => [SpecimenWrapper](/specimenwrapper)
- TaxonomicUnitWrapper.TYPE\_APOMORPHY => reserved for future use
- TaxonomicUnitWrapper.TYPE\_PHYLOREF => reserved for future use

It also contains static methods for extracting taxonomic units from arbitrary strings, such as phylogeny labels.

Every taxonomic unit SHOULD have an rdfs:label and MAY include a dcterm:description to describe it in human-readable terms. It MUST include a '@type' that specifies what type of taxonomic unit it is.

Taxonomic units may be specified with only an '@id' or a set of '@id's, which indicate external references.

---

## Constructor

<Signature
  code="new TaxonomicUnitWrapper(
	tunit,
	defaultNomenCode,
): TaxonomicUnitWrapper"
/>

Wrap a taxonomic unit.

---

## Static Methods

<MemberHeading id="normalize" depth="3" name="normalize" sig="normalize(tunit)" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L62" sourceLabel="TaxonomicUnitWrapper.js:62" />

Normalize the specified taxonomic unit.

**Parameters**

- `tunit` — A taxonomic unit to be normalized.

<MemberHeading id="fromlabel" depth="3" name="fromLabel" sig="fromLabel()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L156" sourceLabel="TaxonomicUnitWrapper.js:156" />

Given a label, attempt to parse it into a taxonomic unit, whether a scientific name or a specimen identifier. The provided nomenclatural code is used.

**Returns**

- A taxonomic unit that this label could be parsed as.

## Instance Fields

<MemberHeading id="types" depth="3" name="types" sig="types" />

<MemberMeta sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L83" sourceLabel="TaxonomicUnitWrapper.js:83" />

What type of specifier is this? This is an array that could contain multiple classes, but should contain one of:

- `TYPE_TAXON_CONCEPT`
- `TYPE_SPECIMEN`

<MemberHeading id="taxonconcept" depth="3" name="taxonConcept" sig="taxonConcept" />

<MemberMeta sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L92" sourceLabel="TaxonomicUnitWrapper.js:92" />

Return this taxonomic unit if it is a taxon concept.

<MemberHeading id="specimen" depth="3" name="specimen" sig="specimen" />

<MemberMeta sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L101" sourceLabel="TaxonomicUnitWrapper.js:101" />

Return this taxonomic unit if it is a specimen.

<MemberHeading id="externalreferences" depth="3" name="externalReferences" sig="externalReferences" />

<MemberMeta sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L113" sourceLabel="TaxonomicUnitWrapper.js:113" />

Return the list of external references for this taxonomic unit. This is just all the '@ids' of this object.

<MemberHeading id="label" depth="3" name="label" sig="label" />

<MemberMeta sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L122" sourceLabel="TaxonomicUnitWrapper.js:122" />

Return the label of this taxonomic unit.

<MemberHeading id="asjson" depth="3" name="asJSON" sig="asJSON" />

<MemberMeta sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L240" sourceLabel="TaxonomicUnitWrapper.js:240" />

Return the JSON representation of this taxonomic unit, i.e. the object we're wrapping.

<MemberHeading id="asjsonld" depth="3" name="asJSONLD" sig="asJSONLD" />

<MemberMeta sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L247" sourceLabel="TaxonomicUnitWrapper.js:247" />

Return this taxonomic unit as an OWL/JSON-LD object.

<MemberHeading id="asowlequivclass" depth="3" name="asOWLEquivClass" sig="asOWLEquivClass" />

<MemberMeta sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L267" sourceLabel="TaxonomicUnitWrapper.js:267" />

Return the equivalent class expression for this taxonomic unit.

## Static Fields

<MemberHeading id="typetaxonconcept" depth="3" name="TYPE_TAXON_CONCEPT" sig="TYPE_TAXON_CONCEPT" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L43" sourceLabel="TaxonomicUnitWrapper.js:43" />

A taxon or taxon concept.

<MemberHeading id="typespecimen" depth="3" name="TYPE_SPECIMEN" sig="TYPE_SPECIMEN" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonomicunitwrapper-js/#L48" sourceLabel="TaxonomicUnitWrapper.js:48" />

A specimen.
