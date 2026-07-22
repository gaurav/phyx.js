---
title: PhylogenyWrapper
kind: class
longname: PhylogenyWrapper
description: Wraps a Phylogeny in a PHYX file and provides access to node, node labels and other information. Remember that a Phylogeny also has the additionalNodeProperties object which provides additional properties for nodes.
---

# PhylogenyWrapper

<SourceLink href="/source/wrappers/phylogenywrapper-js/#L19" label="PhylogenyWrapper.js:19" />

Wraps a Phylogeny in a PHYX file and provides access to node, node labels and other information. Remember that a Phylogeny also has the additionalNodeProperties object which provides additional properties for nodes.

---

## Constructor

<Signature
  code="new PhylogenyWrapper(
	phylogeny,
	defaultNomenCode,
): PhylogenyWrapper"
/>

---

## Instance Methods

<MemberHeading id="gettaxonomicunitsfornodelabel" depth="3" name="getTaxonomicUnitsForNodeLabel" sig="getTaxonomicUnitsForNodeLabel()" />

<MemberMeta sourceHref="/source/wrappers/phylogenywrapper-js/#L224" sourceLabel="PhylogenyWrapper.js:224" />

Return a list of taxonomic units for a node label.

If the additionalNodeProperties for this node label includes taxonomic units (using `representsTaxonomicUnits` = obo:CDAO\_0000187), then those taxonomic units are used. Otherwise, one will be constructed using the default nomenclatural code set up when this PhylogenyWrapper was set up.

## Static Methods

<MemberHeading id="normalize" depth="3" name="normalize" sig="normalize()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/phylogenywrapper-js/#L37" sourceLabel="PhylogenyWrapper.js:37" />

Return a normalized form of the phylogeny.
