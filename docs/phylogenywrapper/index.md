---
title: PhylogenyWrapper
kind: class
longname: PhylogenyWrapper
description: Wraps a Phylogeny in a PHYX file and provides access to node, node labels and other information. Remember that a Phylogeny also has the additionalNodeProperties object which provides additional properties for nodes.
group: Wrappers
order: 3
---

# PhylogenyWrapper

<SourceLink href="/source/wrappers/phylogenywrapper-js/#L20" label="PhylogenyWrapper.js:20" />

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

<MemberMeta sourceHref="/source/wrappers/phylogenywrapper-js/#L225" sourceLabel="PhylogenyWrapper.js:225" />

Return a list of taxonomic units for a node label.

If the additionalNodeProperties for this node label includes taxonomic units (using `representsTaxonomicUnits` = obo:CDAO\_0000187), then those taxonomic units are used. Otherwise, one will be constructed using the default nomenclatural code set up when this PhylogenyWrapper was set up.

## Static Methods

<MemberHeading id="normalize" depth="3" name="normalize" sig="normalize()" />

<MemberMeta badges="static" sourceHref="/source/wrappers/phylogenywrapper-js/#L38" sourceLabel="PhylogenyWrapper.js:38" />

Return a normalized form of the phylogeny.
