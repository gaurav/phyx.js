---
title: TaxonNameWrapper
kind: class
longname: TaxonNameWrapper
description: "Wraps a taxon name to provide access to components of the taxon name. This is based on the TDWG TaxonName standard, as at https://github.com/tdwg/ontology/blob/master/ontology/voc/TaxonName.rdf. Every instance of this class is expected to have some combination of the following fields: rdfs:label -- the verbatim taxon name nameComplete -- the complete uninomial, binomial or trinomial name. nomenclaturalCode -- the nomenclatural code under which the complete name should be interpreted. We will also read the following fields if they are present: uninomial: The uninomial name of this taxon, if one is present. genusPart: The genus name. specificEpithet: The specific epithet. infraspecificEpithet: The infraspecific epithet. We wrap whatever we're given, so we won't assume that these fields are actually consistent with each other. However, when one of these fields are set, we overwrite the nameComplete to ensure that they are consistent. Similarly, changing the nameComplete will overwrite the genusPart, specificEpithet and infraspecificEpithet. Note that the TaxonName ontology recommends dc:title instead of rdfs:label; however, I like the idea of using dc:title for documents and rdfs:label for vocabulary terms, so I'm okay with using rdfs:label for the verbatim name."
---

# TaxonNameWrapper

<SourceLink href="/source/wrappers/taxonnamewrapper-js/#L38" label="TaxonNameWrapper.js:38" />

Wraps a taxon name to provide access to components of the taxon name. This is based on the TDWG TaxonName standard, as at https\://github.com/tdwg/ontology/blob/master/ontology/voc/TaxonName.rdf.

Every instance of this class is expected to have some combination of the following fields:

- rdfs:label -- the verbatim taxon name
- nameComplete -- the complete uninomial, binomial or trinomial name.
- nomenclaturalCode -- the nomenclatural code under which the complete name should be interpreted.

We will also read the following fields if they are present:

- uninomial: The uninomial name of this taxon, if one is present.
- genusPart: The genus name.
- specificEpithet: The specific epithet.
- infraspecificEpithet: The infraspecific epithet.

We wrap whatever we're given, so we won't assume that these fields are actually consistent with each other. However, when one of these fields are set, we overwrite the nameComplete to ensure that they are consistent. Similarly, changing the nameComplete will overwrite the genusPart, specificEpithet and infraspecificEpithet.

Note that the TaxonName ontology recommends dc:title instead of rdfs:label; however, I like the idea of using dc:title for documents and rdfs:label for vocabulary terms, so I'm okay with using rdfs:label for the verbatim name.

---

## Constructor

<Signature code="new TaxonNameWrapper(txname, defaultNomenCode): TaxonNameWrapper" />

Create a new taxon name wrapper around the JSON representation of a taxon name.

---

## Static Methods

<MemberHeading id="getnomenclaturalcodes" depth="3" name="getNomenclaturalCodes" sig="getNomenclaturalCodes()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L96" sourceLabel="TaxonNameWrapper.js:96" />

Return a list of all supported nomenclatural code. Each entry will have the following keys:

- code: A list of short names that can be used to represent this nomenclatural code.
- label: An informal name of this nomenclatural code in English.
- title: The formal name of this nomenclatural code in English.
- iri: The IRI of this nomenclatural code.

This will be used in drawing user interfaces, so this should be in order of likelihood of use.

<MemberHeading id="getnomencodedetails" depth="3" name="getNomenCodeDetails" sig="getNomenCodeDetails()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L142" sourceLabel="TaxonNameWrapper.js:142" />

Returns the nomenclatural code entry for a code.

<MemberHeading id="normalize" depth="3" name="normalize" sig="normalize(txname)" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L163" sourceLabel="TaxonNameWrapper.js:163" />

Normalize the specified taxon name.

**Parameters**

- `txname` — A taxon name to be normalized.

<MemberHeading id="fromverbatimname" depth="3" name="fromVerbatimName" sig="fromVerbatimName()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L207" sourceLabel="TaxonNameWrapper.js:207" />

Parses a verbatim taxon name into an (unwrapped) TaxonName.

## Instance Fields

<MemberHeading id="nomenclaturalcode" depth="3" name="nomenclaturalCode" sig="nomenclaturalCode" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L181" sourceLabel="TaxonNameWrapper.js:181" />

Returns the nomenclatural code of this taxon name.

<MemberHeading id="nomenclaturalcodedetails" depth="3" name="nomenclaturalCodeDetails" sig="nomenclaturalCodeDetails" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L188" sourceLabel="TaxonNameWrapper.js:188" />

Returns the nomenclatural code of this taxon name as a IRI.

<MemberHeading id="nomenclaturalcode" depth="3" name="nomenclaturalCode" sig="nomenclaturalCode" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L200" sourceLabel="TaxonNameWrapper.js:200" />

Set the nomenclatural code of this taxon name.

<MemberHeading id="label" depth="3" name="label" sig="label" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L289" sourceLabel="TaxonNameWrapper.js:289" />

Return the label of this scientific name.

<MemberHeading id="label" depth="3" name="label" sig="label" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L297" sourceLabel="TaxonNameWrapper.js:297" />

Set the label of this scientific name.

<MemberHeading id="verbatimname" depth="3" name="verbatimName" sig="verbatimName" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L308" sourceLabel="TaxonNameWrapper.js:308" />

Return the verbatim name of this taxon name.

<MemberHeading id="namecomplete" depth="3" name="nameComplete" sig="nameComplete" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L316" sourceLabel="TaxonNameWrapper.js:316" />

Return the complete name (i.e. the uninomial, binomial or trinomial name without authority information). Setting this re-parses the provided name.

<MemberHeading id="namecomplete" depth="3" name="nameComplete" sig="nameComplete" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L329" sourceLabel="TaxonNameWrapper.js:329" />

Set the complete name. To do this, we re-parse the provided name.

<MemberHeading id="uninomial" depth="3" name="uninomial" sig="uninomial" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L337" sourceLabel="TaxonNameWrapper.js:337" />

Return the uninomial name if there is one.

<MemberHeading id="uninomial" depth="3" name="uninomial" sig="uninomial" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L357" sourceLabel="TaxonNameWrapper.js:357" />

Set the uninomial name.

<MemberHeading id="binomialname" depth="3" name="binomialName" sig="binomialName" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L363" sourceLabel="TaxonNameWrapper.js:363" />

Return the binomial name if available.

<MemberHeading id="binomialname" depth="3" name="binomialName" sig="binomialName" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L375" sourceLabel="TaxonNameWrapper.js:375" />

Set the binomial name.

<MemberHeading id="trinomialname" depth="3" name="trinomialName" sig="trinomialName" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L381" sourceLabel="TaxonNameWrapper.js:381" />

Return the trinomial name if available.

<MemberHeading id="trinomialname" depth="3" name="trinomialName" sig="trinomialName" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L395" sourceLabel="TaxonNameWrapper.js:395" />

Set the trinomial name.

<MemberHeading id="genuspart" depth="3" name="genusPart" sig="genusPart" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L401" sourceLabel="TaxonNameWrapper.js:401" />

Return the genus part of this scientific name if available.

<MemberHeading id="genuspart" depth="3" name="genusPart" sig="genusPart" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L422" sourceLabel="TaxonNameWrapper.js:422" />

Set the genus part of this name.

<MemberHeading id="specificepithet" depth="3" name="specificEpithet" sig="specificEpithet" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L434" sourceLabel="TaxonNameWrapper.js:434" />

Return the specific epithet of this scientific name if available.

<MemberHeading id="specificepithet" depth="3" name="specificEpithet" sig="specificEpithet" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L455" sourceLabel="TaxonNameWrapper.js:455" />

Set the specificEpithet part of this name.

<MemberHeading id="infraspecificepithet" depth="3" name="infraspecificEpithet" sig="infraspecificEpithet" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L467" sourceLabel="TaxonNameWrapper.js:467" />

Return the infraspecific epithet of this scientific name if available.

<MemberHeading id="infraspecificepithet" depth="3" name="infraspecificEpithet" sig="infraspecificEpithet" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L490" sourceLabel="TaxonNameWrapper.js:490" />

Set the infraspecificEpithet part of this name.

<MemberHeading id="asjsonld" depth="3" name="asJSONLD" sig="asJSONLD" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L504" sourceLabel="TaxonNameWrapper.js:504" />

Return this taxon name in an JSON-LD representation.

<MemberHeading id="asowlequivclass" depth="3" name="asOWLEquivClass" sig="asOWLEquivClass" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L521" sourceLabel="TaxonNameWrapper.js:521" />

Return this taxon name as an OWL equivalentClass expression.

## Static Fields

<MemberHeading id="typetaxonname" depth="3" name="TYPE_TAXON_NAME" sig="TYPE_TAXON_NAME" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L53" sourceLabel="TaxonNameWrapper.js:53" />

The type associated with these taxonName objects.

<MemberHeading id="unknowncode" depth="3" name="UNKNOWN_CODE" sig="UNKNOWN_CODE" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L60" sourceLabel="TaxonNameWrapper.js:60" />

The IRI for an unknown nomenclatural code (i.e. all we know is that it's a scientific name).
