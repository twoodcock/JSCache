[TOC]

# Project Notes:

This is not set up as a released package. It is part of another project,
currently provided here the record.

The test is set up to be run using Jest.

# Implement a Simple Cache Mechanism in JavaScript.

This repository contains a simple JavaScript caching object.

* Instantiate the cache with the desired cache size.
* Cache slots are identified by an object's attributes rather than a string.
* Pass an object with matching attributes, get the cached result back.
* You can provide a set of keyAttributes on cache creation. When you do this,
  only those key attributes are used when storing into and fetching from the
  cache.

```
cache = new Cache({size: 10});
keyProperties = {list: "value", of: "value", keys: "value"};
cache.put(keyProperties, payload);
samePayload = cache.get(keyProperties);
);
```

With key attributes:

```
cache = new Cache({size: 10, keyAttributes=['list', 'value']});
keyProperties1 = {list: "value", of: "value", keys: "value"};
keyProperties2 = {list: "value", of: "value", keys: "value"};
cache.put(keyProperties1, payload);
samePayload = cache.get(keyProperties2);
);
```

## Key Attributes, Why?

The key attributes implementation exists to decouple the cache from the
application. When you apply key attributes to the cache, the application no
longer has to decide what attributes are important.