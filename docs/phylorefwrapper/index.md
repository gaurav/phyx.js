---
title: PhylorefWrapper
kind: class
longname: PhylorefWrapper
description: Wraps a phyloreference in a Phyx model, with multiple specifiers and statuses. Includes code for generating the components of a phyloreference expression in OWL.
---

# PhylorefWrapper

<SourceLink href="/source/wrappers/phylorefwrapper-js/#L16" label="PhylorefWrapper.js:16" />

Wraps a phyloreference in a Phyx model, with multiple specifiers and statuses. Includes code for generating the components of a phyloreference expression in OWL.

---

## Constructor

<Signature
  code="new PhylorefWrapper(
	phyloref,
	phyxDefaultNomenCode,
): PhylorefWrapper"
/>

---

## Instance Methods

<MemberHeading id="createcomponentclass" depth="3" name="createComponentClass" sig="createComponentClass()" />

<MemberMeta sourceHref="/source/wrappers/phylorefwrapper-js/#L434" sourceLabel="PhylorefWrapper.js:434" />

Create a component class for the set of internal and external specifiers provided. We turn this into a label (in the form `A & B ~ C V D`), which we use to ensure that we don't create more than one class for a particular set of internal and external specifiers.

- jsonld: The JSON-LD representation of the Phyloreference this is an component class for. We mainly use this to retrieve its '@id'.
- internalSpecifiers: The set of internal specifiers for this component class.
- externalSpecifiers: The set of external specifiers for this component class.
- equivClass: The equivalent class expression for this component class as a function that returns the expression as a string.
- reusePrevious (default: true): If true, we reuse previous expressions with the same set of included and excluded specifiers. If false, we always generate a new component class for this expression.
- parentClass: If not undefined, provides a JSON-LD definition of the class to set as the parent class of this component class. We only use the \['@id'].

<MemberHeading id="getmrcarestrictionoftwotus" depth="3" name="getMRCARestrictionOfTwoTUs" sig="getMRCARestrictionOfTwoTUs()" />

<MemberMeta sourceHref="/source/wrappers/phylorefwrapper-js/#L548" sourceLabel="PhylorefWrapper.js:548" />

Return an OWL restriction for the most recent common ancestor (MRCA) of two taxonomic units.

## Static Methods

<MemberHeading id="normalize" depth="3" name="normalize" sig="normalize(phyloref)" />

<MemberMeta badges="static" sourceHref="/source/wrappers/phylorefwrapper-js/#L45" sourceLabel="PhylorefWrapper.js:45" />

Normalize a phyloreference.

**Parameters**

- `phyloref`

## Instance Fields

<MemberHeading id="internalspecifiers" depth="3" name="internalSpecifiers" sig="internalSpecifiers" />

<MemberMeta sourceHref="/source/wrappers/phylorefwrapper-js/#L30" sourceLabel="PhylorefWrapper.js:30" />

Return the internal specifiers of this phyloref. If the phyloref doesn't have any, an empty list is stored on it and returned, so that callers can add specifiers by pushing onto it.

<MemberHeading id="externalspecifiers" depth="3" name="externalSpecifiers" sig="externalSpecifiers" />

<MemberMeta sourceHref="/source/wrappers/phylorefwrapper-js/#L63" sourceLabel="PhylorefWrapper.js:63" />

Return the external specifiers of this phyloref. If the phyloref doesn't have any, an empty list is stored on it and returned, so that callers can add specifiers by pushing onto it.

<MemberHeading id="label" depth="3" name="label" sig="label" />

<MemberMeta sourceHref="/source/wrappers/phylorefwrapper-js/#L78" sourceLabel="PhylorefWrapper.js:78" />

Return a label for this phyloreference: its `label` if it has one, failing that the first of its `labels`, failing that its `title`. Setting this always writes to `label`.

<MemberHeading id="label" depth="3" name="label" sig="label" />

<MemberMeta sourceHref="/source/wrappers/phylorefwrapper-js/#L91" sourceLabel="PhylorefWrapper.js:91" />

Set a label for this phyloreference.

<MemberHeading id="specifiers" depth="3" name="specifiers" sig="specifiers" />

<MemberMeta sourceHref="/source/wrappers/phylorefwrapper-js/#L101" sourceLabel="PhylorefWrapper.js:101" />

Return all the specifiers of this phyloref (if any).

<MemberHeading id="uniqnomencodes" depth="3" name="uniqNomenCodes" sig="uniqNomenCodes" />

<MemberMeta sourceHref="/source/wrappers/phylorefwrapper-js/#L373" sourceLabel="PhylorefWrapper.js:373" />

Return a list of all the unique nomenclatural codes used by this phyloreference. The default nomenclatural code used in creating the PhylorefWrapper will be used for any taxonomic units that don't have any nomenclatural code set. If any specifiers are not taxon concepts, they will be represented in the returned list as owlterms.UNKNOWN\_CODE.

<MemberHeading id="defaultnomencode" depth="3" name="defaultNomenCode" sig="defaultNomenCode" />

<MemberMeta sourceHref="/source/wrappers/phylorefwrapper-js/#L399" sourceLabel="PhylorefWrapper.js:399" />

Returns a summarized nomenclatural code for this phyloref. If all of the specifiers have either the same nomenclatural code or `undefined`, this getter will return that nomenclatural code. Otherwise, this method will return owlterms.UNKNOWN\_CODE.
