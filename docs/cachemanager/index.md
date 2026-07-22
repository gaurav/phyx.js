---
title: CacheManager
kind: class
longname: CacheManager
description: phyx.js needs to cache several kinds of data to avoid reparsing them over and over again, such as scientific names. This CacheManager provides that facility, and allows users of this library to clear the cache as needed. We might want to replace this with a cache that limits the amount of memory, such as https://www.npmjs.com/package/safe-memory-cache.
group: Utilities
---

# CacheManager

<SourceLink href="/source/utils/phyxcachemanager-js/#L13" label="PhyxCacheManager.js:13" />

phyx.js needs to cache several kinds of data to avoid reparsing them over and over again, such as scientific names. This CacheManager provides that facility, and allows users of this library to clear the cache as needed.

We might want to replace this with a cache that limits the amount of memory, such as https\://www\.npmjs.com/package/safe-memory-cache.

---

## Constructor

<Signature code="new CacheManager(): CacheManager" />

Construct a new cache manager.

---

## Instance Methods

<MemberHeading id="clear" depth="3" name="clear" sig="clear()" />

<MemberMeta sourceHref="/source/utils/phyxcachemanager-js/#L20" sourceLabel="PhyxCacheManager.js:20" />

Clear all current caches.

<MemberHeading id="has" depth="3" name="has" sig="has()" />

<MemberMeta sourceHref="/source/utils/phyxcachemanager-js/#L25" sourceLabel="PhyxCacheManager.js:25" />

Return true if we have a value for this particular cache key.

<MemberHeading id="get" depth="3" name="get" sig="get()" />

<MemberMeta sourceHref="/source/utils/phyxcachemanager-js/#L30" sourceLabel="PhyxCacheManager.js:30" />

Look up the value of a key in a particular cache.

<MemberHeading id="put" depth="3" name="put" sig="put()" />

<MemberMeta sourceHref="/source/utils/phyxcachemanager-js/#L37" sourceLabel="PhyxCacheManager.js:37" />

Set the value of a key in a particular cache.
