# Resources for Distributed File Storage System

## 📺 Video Tutorials
- [Distributed Systems Course MIT 6.824 (2025 Edition)](https://www.youtube.com/playlist?list=PLrw6a1wE39_tb2fErI4-WkMbsvGQk9_UB) - Complete course - **ESSENTIAL**
- [Building Distributed Systems in 2026](https://www.youtube.com/watch?v=cQP8WApzIQQ) - Fundamentals with modern tools
- [Raft Consensus Explained (2026 Update)](https://www.youtube.com/watch?v=vYp4LYbnnW8) - Interactive visualization
- [HDFS & Modern Distributed File Systems](https://www.youtube.com/watch?v=OHsjRQ9vFv8) - Hadoop filesystem deep dive

## 📚 Written Tutorials
- [Designing Data-Intensive Applications (2nd Edition)](https://dataintensive.net/) - Martin Kleppmann book - **MUST READ**
- [Amazon Dynamo Paper](https://www.allthingsdistributed.com/2007/10/amazons_dynamo.html) - Foundational paper
- [Consistent Hashing Explained](https://www.toptal.com/big-data/consistent-hashing) - Distribution strategy
- [Raft Consensus Algorithm](https://raft.github.io/) - Interactive visualization

## 🔧 Tools & Libraries

### Distributed Coordination
- [etcd](https://etcd.io/) - Distributed key-value store with Raft - **RECOMMENDED**
- [Consul](https://www.consul.io/) - Service mesh and coordination
- [Apache ZooKeeper](https://zookeeper.apache.org/) - Coordination service
- [Raft (Go)](https://github.com/hashicorp/raft) - HashiCorp's Raft implementation

### Communication
- [gRPC](https://grpc.io/) - High-performance RPC framework - **RECOMMENDED**
- [ZeroMQ](https://zeromq.org/) - Asynchronous messaging library
- [NATS](https://nats.io/) - Message-oriented middleware
- [Protocol Buffers](https://protobuf.dev/) - Serialization format

### Storage & I/O
- [MinIO](https://min.io/) - S3-compatible object storage (study implementation)
- [RocksDB](https://rocksdb.org/) - Embedded key-value store
- [BadgerDB](https://github.com/dgraph-io/badger) - Fast KV database in Go
- [BoltDB](https://github.com/etcd-io/bbolt) - Pure Go key-value store

### Monitoring & Observability
- [Prometheus](https://prometheus.io/) - Metrics and alerting - **RECOMMENDED**
- [Grafana](https://grafana.com/) - Visualization dashboards
- [Jaeger](https://www.jaegertracing.io/) - Distributed tracing
- [VictoriaMetrics](https://victoriametrics.com/) - Time-series database

## 💻 GitHub Repositories
- [SeaweedFS](https://github.com/seaweedfs/seaweedfs) - Simple, scalable distributed file system in Go - **STUDY THIS**
- [MinIO](https://github.com/minio/minio) - High-performance object storage
- [Ceph](https://github.com/ceph/ceph) - Distributed storage platform
- [GlusterFS](https://github.com/gluster/glusterfs) - Scalable network filesystem
- [TiKV](https://github.com/tikv/tikv) - Distributed transactional KV database in Rust
- [CockroachDB](https://github.com/cockroachdb/cockroach) - Distributed SQL (study architecture)

## 📖 Learning Resources

### Distributed Systems Theory
- [MIT 6.824](https://pdos.csail.mit.edu/6.824/) - Best distributed systems course - **ESSENTIAL**
- [Distributed Systems for Fun and Profit](http://book.mixu.net/distsys/) - Free online book
- [Jepsen Analyses](https://jepsen.io/analyses) - Real-world consistency testing
- [Papers We Love - Distributed Systems](https://github.com/papers-we-love/papers-we-love/tree/master/distributed_systems)

### Consensus Algorithms
- [Raft Paper](https://raft.github.io/raft.pdf) - Original Raft paper - **MUST READ**
- [Paxos Made Simple](https://lamport.azurewebsites.net/pubs/paxos-simple.pdf) - Leslie Lamport
- [Understanding Raft](https://thesecretlivesofdata.com/raft/) - Interactive visualization
- [Raft Implementation Guide](https://eli.thegreenplace.net/2020/implementing-raft-part-0-introduction/)

### Systems Programming
- [The Go Programming Language](https://www.gopl.io/) - If using Go
- [The Rust Book](https://doc.rust-lang.org/book/) - If using Rust
- [System Design Primer](https://github.com/donnemartin/system-design-primer) - Comprehensive guide
- [High Performance Browser Networking](https://hpbn.co/) - Network optimization

### Storage Systems
- [Google File System Paper](https://static.googleusercontent.com/media/research.google.com/en//archive/gfs-sosp2003.pdf) - GFS design - **FOUNDATIONAL**
- [HDFS Architecture](https://hadoop.apache.org/docs/r1.2.1/hdfs_design.html) - Hadoop design
- [Facebook's Haystack](https://www.usenix.org/legacy/event/osdi10/tech/full_papers/Beaver.pdf) - Photo storage

## 🌐 APIs & Related Services
- [MinIO SDK](https://min.io/docs/minio/linux/developers/minio-drivers.html) - S3-compatible API
- [etcd API](https://etcd.io/docs/v3.5/learning/api/) - Distributed KV operations
- [AWS S3 API](https://docs.aws.amazon.com/s3/index.html) - Reference implementation

## 📚 Research Papers (Must-Read)

### Foundational Papers
1. **[The Google File System](https://static.googleusercontent.com/media/research.google.com/en//archive/gfs-sosp2003.pdf)** (2003) - GFS architecture
2. **[MapReduce](https://static.googleusercontent.com/media/research.google.com/en//archive/mapreduce-osdi04.pdf)** (2004) - Distributed processing
3. **[Dynamo: Amazon's Key-Value Store](https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf)** (2007) - Eventually consistent storage
4. **[Ceph: Scalable Storage](https://ceph.com/assets/pdfs/weil-ceph-osdi06.pdf)** (2006) - Distributed object store
5. **[Raft Consensus](https://raft.github.io/raft.pdf)** (2014) - Understandable consensus

### Advanced Topics
- [Erasure Coding](https://www.usenix.org/system/files/conference/fast14/fast14-paper_huang.pdf) - Storage efficiency
- [Consistent Hashing](https://www.akamai.com/us/en/multimedia/documents/technical-publication/consistent-hashing-and-random-trees-distributed-caching-protocols-for-relieving-hot-spots-on-the-world-wide-web-technical-publication.pdf) - Original paper
- [CAP Theorem](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed/) - 12 years later
- [Vector Clocks](https://haslab.wordpress.com/2011/07/08/version-vectors-are-not-vector-clocks/) - Distributed versioning

## 🛠️ Development & Testing Tools
- [Chaos Monkey](https://netflix.github.io/chaosmonkey/) - Failure injection testing
- [Jepsen](https://github.com/jepsen-io/jepsen) - Distributed systems testing framework
- [Toxiproxy](https://github.com/Shopify/toxiproxy) - Network condition simulation
- [Docker](https://www.docker.com/) - Multi-node local testing
- [Kind](https://kind.sigs.k8s.io/) - Kubernetes in Docker

## 🚀 Consistent Hashing Example (Go)
```go
package main

import (
    "crypto/sha256"
    "encoding/binary"
    "sort"
)

type ConsistentHash struct {
    ring       map[uint64]string // hash -> node
    sortedKeys []uint64
    replicas   int
}

func NewConsistentHash(replicas int) *ConsistentHash {
    return &ConsistentHash{
        ring:     make(map[uint64]string),
        replicas: replicas,
    }
}

func (ch *ConsistentHash) hash(key string) uint64 {
    h := sha256.Sum256([]byte(key))
    return binary.BigEndian.Uint64(h[:])
}

func (ch *ConsistentHash) AddNode(node string) {
    for i := 0; i < ch.replicas; i++ {
        virtualKey := node + "#" + string(rune(i))
        hash := ch.hash(virtualKey)
        ch.ring[hash] = node
        ch.sortedKeys = append(ch.sortedKeys, hash)
    }
    sort.Slice(ch.sortedKeys, func(i, j int) bool {
        return ch.sortedKeys[i] < ch.sortedKeys[j]
    })
}

func (ch *ConsistentHash) GetNode(key string) string {
    if len(ch.ring) == 0 {
        return ""
    }

    hash := ch.hash(key)
    idx := sort.Search(len(ch.sortedKeys), func(i int) bool {
        return ch.sortedKeys[i] >= hash
    })

    if idx == len(ch.sortedKeys) {
        idx = 0
    }

    return ch.ring[ch.sortedKeys[idx]]
}
```

###  📁 File Chunking Example
```
func chunkFile(filePath string, chunkSize int64) ([]Chunk, error) {
    file, err := os.Open(filePath)
    if err != nil {
        return nil, err
    }
    defer file.Close()

    var chunks []Chunk
    buffer := make([]byte, chunkSize)
    chunkIndex := 0

    for {
        n, err := file.Read(buffer)
        if err != nil && err != io.EOF {
            return nil, err
        }
        if n == 0 {
            break
        }

        // Calculate checksum
        checksum := sha256.Sum256(buffer[:n])

        chunk := Chunk{
            Index:    chunkIndex,
            Data:     buffer[:n],
            Checksum: hex.EncodeToString(checksum[:]),
            Size:     int64(n),
        }

        chunks = append(chunks, chunk)
        chunkIndex++
    }

    return chunks, nil
}
```

### 🔄 Replication Example
```
func replicateChunk(chunk Chunk, nodes []Node, replicationFactor int) error {
    var wg sync.WaitGroup
    errors := make(chan error, replicationFactor)

    for i := 0; i < replicationFactor && i < len(nodes); i++ {
        wg.Add(1)
        go func(node Node) {
            defer wg.Done()
            if err := node.StoreChunk(chunk); err != nil {
                errors <- err
            }
        }(nodes[i])
    }

    wg.Wait()
    close(errors)

    // Check if we achieved desired replication
    errorCount := len(errors)
    if errorCount > 0 {
        return fmt.Errorf("replication failed on %d nodes", errorCount)
    }

    return nil
}
```

### 🗺️ Metadata Management Example
```
type FileMetadata struct {
    FileID      string
    FileName    string
    FileSize    int64
    ChunkCount  int
    Chunks      []ChunkMetadata
    Checksum    string
    CreatedAt   time.Time
    ReplicaNodes map[int][]string // chunkIndex -> nodeIDs
}

type ChunkMetadata struct {
    Index     int
    Size      int64
    Checksum  string
    NodeIDs   []string // Where this chunk is stored
}

// Store metadata in etcd
func storeMetadata(client *clientv3.Client, metadata FileMetadata) error {
    ctx, cancel := context.WithTimeout(context.Background(), 5*time.Second)
    defer cancel()

    data, err := json.Marshal(metadata)
    if err != nil {
        return err
    }

    _, err = client.Put(ctx, "/files/"+metadata.FileID, string(data))
    return err
}
```

### 🧪 Chaos Testing Example
```

// Simulate node failure during operation
func TestNodeFailureDuringUpload(t *testing.T) {
    cluster := NewTestCluster(5)
    defer cluster.Shutdown()

    file := generateTestFile(10 * MB)

    // Start upload
    uploadChan := make(chan error)
    go func() {
        uploadChan <- cluster.UploadFile(file)
    }()

    // Kill a node mid-upload
    time.Sleep(100 * time.Millisecond)
    cluster.KillNode(2)

    // Upload should still succeed due to replication
    err := <-uploadChan
    assert.NoError(t, err)

    // Verify file integrity
    downloaded := cluster.DownloadFile(file.ID)
    assert.Equal(t, file.Checksum, downloaded.Checksum)
}
```
