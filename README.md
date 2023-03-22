# Getting Started

### Types of Caching
There are four types of caching are as follows :

1) In-memory Caching.
We use Memcached or Redis, 
Memcached is a simple in-memory cache while Redis is advanced.
2) Database Caching.
   (Hibernate first level cache)
3) Web Server Caching. (Web server caching is a mechanism that stores data for reuse.)
4) CDN Caching (The CDN stands for Content Delivery Network. It is a component used in modern web application, 
across distributed set of caching servers.)

Spring Boot Cache Providers
1) JCache (JSR-107): is the standard caching API for Java. It is provided by javax.cache.spi.CachingProvider.
2) EhCache: The EhCache is an open source Java based cache used to boost performance. It stores the cache in memory and disk (SSD).
EhCache used a file called ehcache.xml.
3) Hazelcast: The Hazelcast is a distributed in-memory data grid structure. It distributes the data equally among all the nodes.
Remember use this spring.hazelcast.config=classpath:config/demo-config.xml and his dependency.
4) Infinispan: is embedded java library. It is used as a cache or a data grid. It stores data in key-value form. It can be easily integrated with JCache, Spring, etc.
Remember use this spring.cache.infinispan.config=infinispan.xml and his dependency.
5) Couchbase: is a NoSQL database that can act as cache provider on top of the spring boot cache abstraction layer.
6) Redis: Redis is a popular in-memory data structure. It is a keystore-based data structure which is used to persist data.
7) Caffeine: Is a high performance Java based caching library. It also provides an in-memory cache.
The spring boot automatically configures the CaffeineCacheManager if Caffeine is found in the classpath
8) Simple: It is the default implementation. It configures a ConcurrentHashMap as a cache store if spring boot does not find any cache provider in the classpath

@Cacheable
Es una anotación a nivel de método. Se utiliza en el método cuya respuesta se va a almacenar en caché

@CachePut
Es una anotación a nivel de método. Se utiliza para actualizar el caché antes de invocar el método. Al hacer esto, el resultado se coloca en el caché y se ejecuta el método

@CacheEvict
Es una anotación a nivel de método. Se utiliza para eliminar los datos de la memoria caché. Cuando el método se anota con esta anotación, el método se ejecuta y la memoria caché se eliminará/desalojará.

¿Podemos usar @CachePut y @Cacheable en el mismo método?
La diferencia entre @Cacheable y @CachePut es que la anotación @Cacheable omite la ejecución del método, mientras que la anotación @CachePut ejecuta el método y coloca su resultado en la memoria caché.

@Caching
Permite múltiples anotaciones de almacenamiento en caché anidadas en el mismo método. Se utiliza cuando queremos utilizar varias anotaciones del mismo tipo.