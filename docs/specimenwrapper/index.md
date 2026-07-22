---
title: SpecimenWrapper
kind: class
longname: SpecimenWrapper
description: "The SpecimenWrapper wraps specimen taxonomic units. These can be identified with a '@type' of SpecimenWrapper.TYPE_SPECIMEN (which is currently https://dwc.tdwg.org/terms/#occurrence). TaxonomicUnitWrapper.TYPE_SPECIMEN: A specimen. Based on http://rs.tdwg.org/dwc/terms/Occurrence Should have a occurrenceID with the occurrence identifier. Should have a basisOfRecord to indicate what sort of occurrence this is. Since TaxonNameWrapper follows the TDWG ontology, we'd love to do the same for SpecimenWrapper, but unfortunately the TaxonOccurrence ontology has been deprecated (see https://github.com/tdwg/ontology). Therefore, it instead improvises a representation based on dwc:Occurrence."
---

# SpecimenWrapper

<SourceLink href="/source/wrappers/specimenwrapper-js/#L21" label="SpecimenWrapper.js:21" />

The SpecimenWrapper wraps specimen taxonomic units. These can be identified with a '@type' of SpecimenWrapper.TYPE\_SPECIMEN (which is currently https\://dwc.tdwg.org/terms/#occurrence).

- TaxonomicUnitWrapper.TYPE\_SPECIMEN: A specimen.

  - Based on http\://rs.tdwg.org/dwc/terms/Occurrence
  - Should have a occurrenceID with the occurrence identifier.
  - Should have a basisOfRecord to indicate what sort of occurrence this is.

Since TaxonNameWrapper follows the TDWG ontology, we'd love to do the same for SpecimenWrapper, but unfortunately the TaxonOccurrence ontology has been deprecated (see https\://github.com/tdwg/ontology). Therefore, it instead improvises a representation based on dwc:Occurrence.

---

## Constructor

<Signature code="new SpecimenWrapper(specimen): SpecimenWrapper" />

Construct a wrapper around a specimen.

---

## Static Methods

<MemberHeading id="normalize" depth="3" name="normalize" sig="normalize(specimen)" />

<MemberMeta badges="static" sourceHref="/source/wrappers/specimenwrapper-js/#L36" sourceLabel="SpecimenWrapper.js:36" />

Normalize the specified specimen.

**Parameters**

- `specimen` — A specimen to be normalized.

<MemberHeading id="fromoccurrenceid" depth="3" name="fromOccurrenceID" sig="fromOccurrenceID()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/specimenwrapper-js/#L57" sourceLabel="SpecimenWrapper.js:57" />

Parse the provided occurrence ID. The two expected formats are:

- 'urn:catalog:\[institutionCode]:\[collectionCode]:\[catalogNumber]' (in which case, we ignore the first two "components" here)
- '\[institutionCode]:\[collectionCode]:\[catalogNumber]'

## Instance Fields

<MemberHeading id="catalognumber" depth="3" name="catalogNumber" sig="catalogNumber" />

<MemberMeta sourceHref="/source/wrappers/specimenwrapper-js/#L118" sourceLabel="SpecimenWrapper.js:118" />

Get the catalogNumber if present.

<MemberHeading id="institutioncode" depth="3" name="institutionCode" sig="institutionCode" />

<MemberMeta sourceHref="/source/wrappers/specimenwrapper-js/#L136" sourceLabel="SpecimenWrapper.js:136" />

Get the institutionCode if present.

<MemberHeading id="collectioncode" depth="3" name="collectionCode" sig="collectionCode" />

<MemberMeta sourceHref="/source/wrappers/specimenwrapper-js/#L155" sourceLabel="SpecimenWrapper.js:155" />

Get the collectionCode if present.

<MemberHeading id="occurrenceid" depth="3" name="occurrenceID" sig="occurrenceID" />

<MemberMeta sourceHref="/source/wrappers/specimenwrapper-js/#L177" sourceLabel="SpecimenWrapper.js:177" />

Return the occurrence ID of this specimen, if we have one. Otherwise, we attempt to construct one in the form: "urn:catalog:" + institutionCode (if present) + ':' + collectionCode (if present) + ':' + catalogNumber (if present)

<MemberHeading id="basisofrecord" depth="3" name="basisOfRecord" sig="basisOfRecord" />

<MemberMeta sourceHref="/source/wrappers/specimenwrapper-js/#L205" sourceLabel="SpecimenWrapper.js:205" />

Return the basis of record, if one is present. See http\://rs.tdwg.org/dwc/terms/basisOfRecord for recommended values.

<MemberHeading id="basisofrecord" depth="3" name="basisOfRecord" sig="basisOfRecord" />

<MemberMeta sourceHref="/source/wrappers/specimenwrapper-js/#L215" sourceLabel="SpecimenWrapper.js:215" />

Set the basis of record. See http\://rs.tdwg.org/dwc/terms/basisOfRecord for recommended values.

<MemberHeading id="taxonconcept" depth="3" name="taxonConcept" sig="taxonConcept" />

<MemberMeta sourceHref="/source/wrappers/specimenwrapper-js/#L220" sourceLabel="SpecimenWrapper.js:220" />

Return this specimen as a taxon concept if it contains taxon name information.

<MemberHeading id="label" depth="3" name="label" sig="label" />

<MemberMeta sourceHref="/source/wrappers/specimenwrapper-js/#L227" sourceLabel="SpecimenWrapper.js:227" />

Return a label for this specimen.

<MemberHeading id="asowlequivclass" depth="3" name="asOWLEquivClass" sig="asOWLEquivClass" />

<MemberMeta sourceHref="/source/wrappers/specimenwrapper-js/#L242" sourceLabel="SpecimenWrapper.js:242" />

Return this specimen as an equivalentClass expression.

## Static Fields

<MemberHeading id="typespecimen" depth="3" name="TYPE_SPECIMEN" sig="TYPE_SPECIMEN" />

<MemberMeta badges="static" sourceHref="/source/wrappers/specimenwrapper-js/#L23" sourceLabel="SpecimenWrapper.js:23" />

The '@type' of specimens in JSON-LD document.
