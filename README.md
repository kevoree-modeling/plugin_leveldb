# KMF Storage Plugin: LevelDB backend

This KMF plugin aims at offering an efficient file based storage, embeddable directly in your JVM-based application. 
This backend is also available for Android usages.
LevelDB offers a very efficient storage that can handle billions of KMF elements on a single machine based storage.
This plugin does not rely on an external server.
This feature both boost the performance by avoiding network or Inter-Processus communications and in addition sipplify a lot the configuration because only require a target directory to persist model on disk.

## Dependency

Simply add the following dependency to your maven project:

```java
<dependency>
    <groupId>org.kevoree.modeling.plugin</groupId>
    <artifactId>leveldb</artifactId>
    <version>4.27.0</version>
</dependency>
```

## Usage

The LevelDBPlugin is the main entry point for this plugin.
Simply reference the full qualified name of the storage (should be an existant directory).

```java
org.kevoree.modeling.cdn.KContentDeliveryDriver levelDBDriver = 
	new org.kevoree.modeling.plugin.LevelDBPlugin("/opt/kmf_storage");
model = new MyModel(DataManagerBuilder.create().withContentDeliveryDriver(levelDBDriver).build(););

```

To have more information about KMF Storage Plugin using, please visit the following tutorial step:

https://github.com/kevoree-modeling/tutorial/tree/master/step2_persistence