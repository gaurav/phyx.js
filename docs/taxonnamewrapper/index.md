---
title: TaxonNameWrapper
kind: class
longname: TaxonNameWrapper
description: "Wraps a taxon name to provide access to components of the taxon name. This is based on the TDWG TaxonName standard, as at https://github.com/tdwg/ontology/blob/master/ontology/voc/TaxonName.rdf. Every instance of this class is expected to have some combination of the following fields: rdfs:label -- the verbatim taxon name nameComplete -- the complete uninomial, binomial or trinomial name. nomenclaturalCode -- the nomenclatural code under which the complete name should be interpreted. We will also read the following fields if they are present: uninomial: The uninomial name of this taxon, if one is present. genusPart: The genus name. specificEpithet: The specific epithet. infraspecificEpithet: The infraspecific epithet. We wrap whatever we're given, so we won't assume that these fields are actually consistent with each other. However, when one of these fields are set, we overwrite the nameComplete to ensure that they are consistent. Similarly, changing the nameComplete will overwrite the genusPart, specificEpithet and infraspecificEpithet. Note that the TaxonName ontology recommends dc:title instead of rdfs:label; however, I like the idea of using dc:title for documents and rdfs:label for vocabulary terms, so I'm okay with using rdfs:label for the verbatim name."
group: Wrappers
---

# TaxonNameWrapper

<SourceLink href="/source/wrappers/taxonnamewrapper-js/#L39" label="TaxonNameWrapper.js:39" />

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

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L97" sourceLabel="TaxonNameWrapper.js:97" />

Return a list of all supported nomenclatural code. Each entry will have the following keys:

- code: A list of short names that can be used to represent this nomenclatural code.
- label: An informal name of this nomenclatural code in English.
- title: The formal name of this nomenclatural code in English.
- iri: The IRI of this nomenclatural code.

This will be used in drawing user interfaces, so this should be in order of likelihood of use.

<MemberHeading id="getnomencodedetails" depth="3" name="getNomenCodeDetails" sig="getNomenCodeDetails()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L143" sourceLabel="TaxonNameWrapper.js:143" />

Returns the nomenclatural code entry for a code.

<MemberHeading id="normalize" depth="3" name="normalize" sig="normalize(txname)" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L164" sourceLabel="TaxonNameWrapper.js:164" />

Normalize the specified taxon name.

**Parameters**

- `txname` — A taxon name to be normalized.

<MemberHeading id="fromverbatimname" depth="3" name="fromVerbatimName" sig="fromVerbatimName()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L208" sourceLabel="TaxonNameWrapper.js:208" />

Parses a verbatim taxon name into an (unwrapped) TaxonName.

## Instance Fields

<MemberHeading id="nomenclaturalcode" depth="3" name="nomenclaturalCode" sig="nomenclaturalCode" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L182" sourceLabel="TaxonNameWrapper.js:182" />

Returns the nomenclatural code of this taxon name.

<MemberHeading id="nomenclaturalcodedetails" depth="3" name="nomenclaturalCodeDetails" sig="nomenclaturalCodeDetails" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L189" sourceLabel="TaxonNameWrapper.js:189" />

Returns the nomenclatural code of this taxon name as a IRI.

<MemberHeading id="nomenclaturalcode" depth="3" name="nomenclaturalCode" sig="nomenclaturalCode" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L201" sourceLabel="TaxonNameWrapper.js:201" />

Set the nomenclatural code of this taxon name.

<MemberHeading id="label" depth="3" name="label" sig="label" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L290" sourceLabel="TaxonNameWrapper.js:290" />

Return the label of this scientific name.

<MemberHeading id="label" depth="3" name="label" sig="label" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L298" sourceLabel="TaxonNameWrapper.js:298" />

Set the label of this scientific name.

<MemberHeading id="verbatimname" depth="3" name="verbatimName" sig="verbatimName" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L309" sourceLabel="TaxonNameWrapper.js:309" />

Return the verbatim name of this taxon name.

<MemberHeading id="namecomplete" depth="3" name="nameComplete" sig="nameComplete" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L317" sourceLabel="TaxonNameWrapper.js:317" />

Return the complete name (i.e. the uninomial, binomial or trinomial name without authority information). Setting this re-parses the provided name.

<MemberHeading id="namecomplete" depth="3" name="nameComplete" sig="nameComplete" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L330" sourceLabel="TaxonNameWrapper.js:330" />

Set the complete name. To do this, we re-parse the provided name.

<MemberHeading id="uninomial" depth="3" name="uninomial" sig="uninomial" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L338" sourceLabel="TaxonNameWrapper.js:338" />

Return the uninomial name if there is one.

<MemberHeading id="uninomial" depth="3" name="uninomial" sig="uninomial" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L358" sourceLabel="TaxonNameWrapper.js:358" />

Set the uninomial name.

<MemberHeading id="binomialname" depth="3" name="binomialName" sig="binomialName" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L364" sourceLabel="TaxonNameWrapper.js:364" />

Return the binomial name if available.

<MemberHeading id="binomialname" depth="3" name="binomialName" sig="binomialName" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L376" sourceLabel="TaxonNameWrapper.js:376" />

Set the binomial name.

<MemberHeading id="trinomialname" depth="3" name="trinomialName" sig="trinomialName" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L382" sourceLabel="TaxonNameWrapper.js:382" />

Return the trinomial name if available.

<MemberHeading id="trinomialname" depth="3" name="trinomialName" sig="trinomialName" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L396" sourceLabel="TaxonNameWrapper.js:396" />

Set the trinomial name.

<MemberHeading id="genuspart" depth="3" name="genusPart" sig="genusPart" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L402" sourceLabel="TaxonNameWrapper.js:402" />

Return the genus part of this scientific name if available.

<MemberHeading id="genuspart" depth="3" name="genusPart" sig="genusPart" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L423" sourceLabel="TaxonNameWrapper.js:423" />

Set the genus part of this name.

<MemberHeading id="specificepithet" depth="3" name="specificEpithet" sig="specificEpithet" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L435" sourceLabel="TaxonNameWrapper.js:435" />

Return the specific epithet of this scientific name if available.

<MemberHeading id="specificepithet" depth="3" name="specificEpithet" sig="specificEpithet" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L456" sourceLabel="TaxonNameWrapper.js:456" />

Set the specificEpithet part of this name.

<MemberHeading id="infraspecificepithet" depth="3" name="infraspecificEpithet" sig="infraspecificEpithet" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L468" sourceLabel="TaxonNameWrapper.js:468" />

Return the infraspecific epithet of this scientific name if available.

<MemberHeading id="infraspecificepithet" depth="3" name="infraspecificEpithet" sig="infraspecificEpithet" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L491" sourceLabel="TaxonNameWrapper.js:491" />

Set the infraspecificEpithet part of this name.

<MemberHeading id="asjsonld" depth="3" name="asJSONLD" sig="asJSONLD" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L505" sourceLabel="TaxonNameWrapper.js:505" />

Return this taxon name in an JSON-LD representation.

<MemberHeading id="asowlequivclass" depth="3" name="asOWLEquivClass" sig="asOWLEquivClass" />

<MemberMeta sourceHref="/source/wrappers/taxonnamewrapper-js/#L522" sourceLabel="TaxonNameWrapper.js:522" />

Return this taxon name as an OWL equivalentClass expression.

## Static Fields

<MemberHeading id="typetaxonname" depth="3" name="TYPE_TAXON_NAME" sig="TYPE_TAXON_NAME" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L54" sourceLabel="TaxonNameWrapper.js:54" />

The type associated with these taxonName objects.

<MemberHeading id="unknowncode" depth="3" name="UNKNOWN_CODE" sig="UNKNOWN_CODE" />

<MemberMeta badges="static" sourceHref="/source/wrappers/taxonnamewrapper-js/#L61" sourceLabel="TaxonNameWrapper.js:61" />

The IRI for an unknown nomenclatural code (i.e. all we know is that it's a scientific name).
