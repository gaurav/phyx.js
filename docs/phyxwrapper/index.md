---
title: PhyxWrapper
kind: class
longname: PhyxWrapper
description: The PhyxWrapper wraps an entire Phyx document.
group: Wrappers
order: 1
---

# PhyxWrapper

<SourceLink href="/source/wrappers/phyxwrapper-js/#L21" label="PhyxWrapper.js:21" />

The PhyxWrapper wraps an entire Phyx document.

---

## Constructor

<Signature
  code="new PhyxWrapper(
	phyx: Object,
	newickParser?: function,
): PhyxWrapper"
/>

Wraps an entire PHYX document.

**Parameters**

- `phyx` (Object) — The Phyx structure to wrap.
- `newickParser` (function, optional, default: "PhylogenyWrapper.getParsedNewick") — A method that accepts a Newick string and returns a list of nodes. Each node should have a 'children' key with its children and optionally a 'name' key with its label. This code previously depended on phylotree.js, whose newick\_parser() function works exactly like this. This option allows you to drop in Phylotree's newick\_parser() or -- if you prefer -- any other option.

---

## Instance Methods

<MemberHeading id="asjsonld" depth="3" name="asJSONLD" sig="asJSONLD(baseIRI?: string): Object" />

<MemberMeta sourceHref="/source/wrappers/phyxwrapper-js/#L103" sourceLabel="PhyxWrapper.js:103" />

Generate an executable ontology from this Phyx document. The document is mostly in JSON-LD already, except for three important things:

1. We have to convert all phylogenies into a series of statements relating to the nodes inside these phylogenies.
1. We have to convert phylogenies into OWL restrictions.
1. Insert all matches between taxonomic units in this file.

**Parameters**

- `baseIRI` (string, optional, default: "\\"\\"") — The base IRI to use when generating this Phyx document. This should include a trailing '#' or '/'. Use '' to indicate that relative IDs should be generated in the produced ontology (e.g. '#phylogeny1'). Note that if a baseIRI is provided, then relative IDs already in the Phyx file (identified by an initial '#') will be turned into absolute IDs by removing the initial `#` and prepending them with the baseIRI.

**Returns**

- `Object` — This Phyx document as an OWL ontology as a JSON-LD object.

<MemberHeading id="tordf" depth="3" name="toRDF" sig="toRDF(baseIRI?: string, filePath?: string): Promise.<string>" />

<MemberMeta sourceHref="/source/wrappers/phyxwrapper-js/#L311" sourceLabel="PhyxWrapper.js:311" />

Generate an executable ontology from this Phyx document as N-Quads. Under the hood, we generate an OWL/JSON-LD representation of this Phyx document, and then convert it into N-Quads so that OWLAPI-supporting tools can directly consume it.

**Parameters**

- `baseIRI` (string, optional, default: "\\"\\"") — The base IRI to use when generating this Phyx document. This should include a trailing '#' or '/'. Use '' to indicate that relative IDs should be generated in the produced ontology (e.g. '#phylogeny1'). Note that if a baseIRI is provided, then relative IDs already in the Phyx file (identified by an initial '#') will be turned into absolute IDs by removing the initial `#` and prepending them with the baseIRI.
- `filePath` (string, optional) — The path of the Phyx file being converted. Used only if the `@context` of the file is a relative path.

**Returns**

- `Promise.<string>` — A Promise to return this Phyx document as a string that can be written to an N-Quads file.

## Static Methods

<MemberHeading id="normalize" depth="3" name="normalize" sig="normalize()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/phyxwrapper-js/#L69" sourceLabel="PhyxWrapper.js:69" />

Return a provided Phyx document as a normalized JSON document. We ignore most keys -- including keys we don't know -- but any key that can be wrapped by one of the other Wrappers in this package will be wrapped and normalized before being returned.

Normalization is mostly needed for TaxonomicUnitWrappers and its subclasses (TaxonConceptWrapper, TaxonNameWrapper), since these can be represented in several essentially identical ways. But if we implement it at every level, we can implement comparison code in Klados easily.

Two Phyx documents should -- upon being normalized -- be comparable with each other with lodash.deepEqual().
