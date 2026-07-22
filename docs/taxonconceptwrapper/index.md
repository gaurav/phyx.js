---
title: TaxonConceptWrapper
kind: class
longname: TaxonConceptWrapper
description: "The TaxonConceptWrapper wraps taxon concepts. These are taxonomic units with a type of TaxonomicUnitWrapper.TYPE_TAXON_CONCEPT. They are based on the Taxon Concept ontology at https://github.com/tdwg/ontology/tree/master/ontology/voc. A taxon concept: SHOULD have a hasName property indicating the name this taxon refers to. MAY have accordingTo, describedBy or circumscribedBy to indicate how this taxon concept should be circumscribed. If none of these are present, this taxonomic unit will be considered a taxon rather than a taxon concept (i.e. as a nominal taxon concept, as in https://github.com/darwin-sw/dsw/wiki/ClassTaxon). MAY have nameString and accordingToString properties. We will fall back to these properties if hasName or accordingTo are missing."
---

# TaxonConceptWrapper

<SourceLink href="/source/wrappers/taxonconceptwrapper-js/#L25" label="TaxonConceptWrapper.js:25" />

The TaxonConceptWrapper wraps taxon concepts. These are taxonomic units with a type of TaxonomicUnitWrapper.TYPE\_TAXON\_CONCEPT. They are based on the Taxon Concept ontology at https\://github.com/tdwg/ontology/tree/master/ontology/voc.

A taxon concept:

- SHOULD have a hasName property indicating the name this taxon refers to.
- MAY have accordingTo, describedBy or circumscribedBy to indicate how this taxon concept should be circumscribed. If none of these are present, this taxonomic unit will be considered a taxon rather than a taxon concept (i.e. as a nominal taxon concept, as in https\://github.com/darwin-sw/dsw/wiki/ClassTaxon).
- MAY have nameString and accordingToString properties. We will fall back to these properties if hasName or accordingTo are missing.

---

## Constructor

<Signature
  code="new TaxonConceptWrapper(
	tunit,
	defaultNomenCode,
): TaxonConceptWrapper"
/>

Create a TaxonConceptWrapper around a taxon concept.

---

## Static Methods

<MemberHeading id="normalize" depth="3" name="normalize" sig="normalize(tc)" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonconceptwrapper-js/#L41" sourceLabel="TaxonConceptWrapper.js:41" />

Normalize the specified taxon concept.

**Parameters**

- `tc` — A taxon concept to be normalized.

<MemberHeading id="fromlabel" depth="3" name="fromLabel" sig="fromLabel()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonconceptwrapper-js/#L178" sourceLabel="TaxonConceptWrapper.js:178" />

Given a node label, attempt to parse it as a scientific name.

Note that this is NOT memoized -- you should really be using TaxonomicUnitWrapper.fromLabel() or TaxonNameWrapper.fromVerbatimName() rather than calling this directly.

**Returns**

- A taxonomic unit that corresponds to this taxon concept.

<MemberHeading id="wraptaxonname" depth="3" name="wrapTaxonName" sig="wrapTaxonName()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonconceptwrapper-js/#L204" sourceLabel="TaxonConceptWrapper.js:204" />

Wrap a taxon name with a particular TaxonName object and an accordingTo (string).

## Instance Fields

<MemberHeading id="taxonname" depth="3" name="taxonName" sig="taxonName" />

<MemberMeta sourceHref="/source/wrappers/taxonconceptwrapper-js/#L57" sourceLabel="TaxonConceptWrapper.js:57" />

Return the taxon name of this taxon concept (if any) as an object.

<MemberHeading id="namecomplete" depth="3" name="nameComplete" sig="nameComplete" />

<MemberMeta sourceHref="/source/wrappers/taxonconceptwrapper-js/#L76" sourceLabel="TaxonConceptWrapper.js:76" />

Return the complete taxon name of this taxon concept (if any), which is the uninomial, binomial or trinomial name.

<MemberHeading id="nomencode" depth="3" name="nomenCode" sig="nomenCode" />

<MemberMeta sourceHref="/source/wrappers/taxonconceptwrapper-js/#L96" sourceLabel="TaxonConceptWrapper.js:96" />

Return the nomenclatural code of this taxon concept as a string.

<MemberHeading id="nomencodedetails" depth="3" name="nomenCodeDetails" sig="nomenCodeDetails" />

<MemberMeta sourceHref="/source/wrappers/taxonconceptwrapper-js/#L107" sourceLabel="TaxonConceptWrapper.js:107" />

Return the nomenclatural code of this taxon concept as an object.

<MemberHeading id="accordingto" depth="3" name="accordingTo" sig="accordingTo" />

<MemberMeta sourceHref="/source/wrappers/taxonconceptwrapper-js/#L121" sourceLabel="TaxonConceptWrapper.js:121" />

Return the accordingTo information (if any) as an object.

For now, we return this verbatim. Once we close #15, we should parse raw labels with a CitationWrapper.

<MemberHeading id="accordingtostring" depth="3" name="accordingToString" sig="accordingToString" />

<MemberMeta sourceHref="/source/wrappers/taxonconceptwrapper-js/#L139" sourceLabel="TaxonConceptWrapper.js:139" />

Return the accordingTo information (if any) as a string.

For now, we stringify objects by converting them into JSON strings. Once we close #15, we will be able to generate a label using CitationWrapper.

<MemberHeading id="label" depth="3" name="label" sig="label" />

<MemberMeta sourceHref="/source/wrappers/taxonconceptwrapper-js/#L155" sourceLabel="TaxonConceptWrapper.js:155" />

Return the label of this taxon concept.

<MemberHeading id="asowlequivclass" depth="3" name="asOWLEquivClass" sig="asOWLEquivClass" />

<MemberMeta sourceHref="/source/wrappers/taxonconceptwrapper-js/#L219" sourceLabel="TaxonConceptWrapper.js:219" />

Return how this class should look in an OWL equivalentClass expression.

Note that we don't include the accordingTo information in this query, since we don't have a useful way to use that during OWL reasoning.

## Static Fields

<MemberHeading id="typetaxonconcept" depth="3" name="TYPE_TAXON_CONCEPT" sig="TYPE_TAXON_CONCEPT" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonconceptwrapper-js/#L27" sourceLabel="TaxonConceptWrapper.js:27" />

The @type of a taxon or taxon concept.
