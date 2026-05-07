# Resources for Real-time Collaborative Editor

## 📺 Video Tutorials
- [Build a Real-time Collaborative Editor with Yjs & TipTap](https://www.youtube.com/watch?v=eW0HQIqzkYQ) - Complete tutorial with Yjs (2025 edition)
- [CRDTs Explained by Martin Kleppmann](https://www.youtube.com/watch?v=x7drE24geUw) - Martin Kleppmann on CRDTs
- [Operational Transformation vs CRDTs](https://www.youtube.com/watch?v=SqP5KNdAkdk) - OT algorithm explained
- [ProseMirror + Yjs Collaborative Editing](https://www.youtube.com/watch?v=9FE0a5W0tIw) - Rich text editor guide

## 📚 Written Tutorials
- [Building a Collaborative Editor with Yjs & TipTap](https://www.freecodecamp.org/news/how-to-build-a-collaborative-text-editor/) - freeCodeCamp guide (updated 2026)
- [CRDTs: The Hard Parts](https://martin.kleppmann.com/2020/07/06/crdt-hard-parts-hydra.html) - Martin Kleppmann
- [Operational Transformation Explained](https://operational-transformation.github.io/) - Complete OT guide
- [Yjs Documentation](https://docs.yjs.dev/) - Official Yjs CRDT library docs

## 🔧 Tools & Libraries

### CRDT Libraries
- [Yjs](https://github.com/yjs/yjs) - High-performance CRDT implementation - **RECOMMENDED**
- [Automerge](https://github.com/automerge/automerge) - JSON-like CRDT
- [Gun.js](https://gun.eco/) - Decentralized graph database with CRDT
- [Y-WebRTC](https://github.com/yjs/y-webrtc) - Yjs with WebRTC for P2P

### Operational Transformation
- [ShareDB](https://github.com/share/sharedb) - Real-time database with OT - **ALTERNATIVE**
- [OT.js](https://github.com/Operational-Transformation/ot.js) - Pure OT implementation

### Rich Text Editors
- [ProseMirror](https://prosemirror.net/) - Modular rich text toolkit - **RECOMMENDED**
- [TipTap](https://tiptap.dev/) - ProseMirror-based editor (easier API) - **RECOMMENDED**
- [Slate.js](https://www.slatejs.org/) - Customizable framework
- [Quill](https://quilljs.com/) - Rich text editor (simpler, less flexible)

### Real-time Communication
- [Socket.io](https://socket.io/) - WebSocket library
- [WebRTC](https://webrtc.org/) - Peer-to-peer connections
- [Liveblocks](https://liveblocks.io/) - Managed collaborative platform (commercial)
- [Partykit](https://www.partykit.io/) - Real-time infrastructure

## 💻 GitHub Repositories
- [Yjs Demos](https://github.com/yjs/yjs-demos) - Official Yjs examples - **STUDY THIS**
- [TipTap](https://github.com/ueberdosis/tiptap) - Modern collaborative editor
- [Notion Clone with Yjs](https://github.com/konstantinmuenster/notion-clone) - Advanced example
- [ProseMirror Examples](https://github.com/ProseMirror/prosemirror-example-setup) - Official examples
- [Google Docs Clone](https://github.com/topics/collaborative-editor) - Various implementations
- [Excalidraw](https://github.com/excalidraw/excalidraw) - Collaborative whiteboard (CRDT)

## 📖 Learning Resources

### CRDT Theory
- [CRDTs: Consistency without Concurrency Control](https://arxiv.org/abs/0907.0929) - Original paper
- [A Comprehensive Study of CRDTs](https://crdt.tech/) - CRDT documentation hub - **ESSENTIAL**
- [Conflict-free Replicated Data Types](https://www.youtube.com/watch?v=yCcWpzY8dIA) - Martin Kleppmann talk
- [CRDT Primer for Distributed Systems](https://www.infoq.com/articles/crdt-distributed-systems/)

### Operational Transformation
- [Understanding OT](https://operational-transformation.github.io/what-is-ot.html) - Complete guide
- [Google Wave OT Paper](https://svn.apache.org/repos/asf/incubator/wave/whitepapers/operational-transform/operational-transform.html)
- [Consistency Maintenance in Real-Time Collaborative Editing](https://www3.ntu.edu.sg/home/czsun/projects/otfaq/) - FAQ and deep dive

### Rich Text Editing
- [ProseMirror Guide](https://prosemirror.net/docs/guide/) - Official comprehensive guide
- [Building a Rich Text Editor](https://www.slatejs.org/walkthroughs/01-installing-slate) - Slate walkthrough
- [ContentEditable: The Good Parts](https://medium.engineering/why-contenteditable-is-terrible-122d8a40e480) - Understanding challenges

### Distributed Systems
- [Eventual Consistency](https://www.allthingsdistributed.com/2008/12/eventually_consistent.html) - Werner Vogels
- [Vector Clocks Explained](https://riak.com/posts/technical/vector-clocks-revisited/) - Causal ordering
- [Byzantine Fault Tolerance](https://pmg.csail.mit.edu/papers/osdi99.pdf) - Advanced consensus

## 🌐 APIs & Services
- [Liveblocks](https://liveblocks.io/) - Managed collaborative infrastructure (paid)
- [Partykit](https://www.partykit.io/) - Real-time servers (free tier)
- [Ably](https://ably.com/) - Real-time messaging platform
- [Pusher](https://pusher.com/) - WebSocket service

## 📚 Research Papers (Essential Reading)

### CRDTs
1. **[Conflict-free Replicated Data Types](https://arxiv.org/abs/0907.0929)** - Shapiro et al. (2011) - **FOUNDATIONAL**
2. **[A Comprehensive Study of CRDTs](https://hal.inria.fr/inria-00555588/document)** - Shapiro et al. (2011)
3. **[Deep Dive into Yjs](https://www.researchgate.net/publication/310212186_Near_Real-Time_Peer-to-Peer_Shared_Editing_on_Extensible_Data_Types)** - Yjs architecture

### Operational Transformation
1. **[Operational Transformation in Real-Time Collaborative Editing](https://dl.acm.org/doi/10.1145/215585.215706)** - Ellis & Gibbs (1989)
2. **[Google Wave OT](https://svn.apache.org/repos/asf/incubator/wave/whitepapers/operational-transform/operational-transform.html)** - Google's implementation
3. **[Consistency Maintenance in Real-Time Collaborative Editing](https://lively-kernel.org/repository/webwerkstatt/projects/Collaboration/paper/Jupiter.pdf)** - Jupiter algorithm

## 🚀 Yjs Integration Example
```typescript
import * as Y from 'yjs';
import { WebsocketProvider } from 'y-websocket';
import { Editor } from '@tiptap/core';
import Collaboration from '@tiptap/extension-collaboration';
import CollaborationCursor from '@tiptap/extension-collaboration-cursor';

// Create Yjs document
const ydoc = new Y.Doc();

// Connect to WebSocket server
const provider = new WebsocketProvider(
  'ws://localhost:1234',
  'my-document-id',
  ydoc
);

// Create TipTap editor with collaboration
const editor = new Editor({
  extensions: [
    Collaboration.configure({
      document: ydoc,
    }),
    CollaborationCursor.configure({
      provider,
      user: {
        name: 'User Name',
        color: '#f783ac',
      },
    }),
  ],
});

// Awareness (presence)
provider.awareness.setLocalStateField('user', {
  name: 'User Name',
  color: '#f783ac',
});

// Listen to changes
provider.awareness.on('change', () => {
  const states = provider.awareness.getStates();
  console.log('Users online:', states.size);
});

```

### 🔧 ProseMirror Schema Example
```JavaScript
import { Schema } from 'prosemirror-model';

const schema = new Schema({
  nodes: {
    doc: { content: 'block+' },
    paragraph: {
      content: 'inline*',
      group: 'block',
      parseDOM: [{ tag: 'p' }],
      toDOM: () => ['p', 0],
    },
    text: { group: 'inline' },
    heading: {
      attrs: { level: { default: 1 } },
      content: 'inline*',
      group: 'block',
      parseDOM: [
        { tag: 'h1', attrs: { level: 1 } },
        { tag: 'h2', attrs: { level: 2 } },
        { tag: 'h3', attrs: { level: 3 } },
      ],
      toDOM: (node) => ['h' + node.attrs.level, 0],
    },
  },
  marks: {
    bold: {
      parseDOM: [{ tag: 'strong' }],
      toDOM: () => ['strong', 0],
    },
    italic: {
      parseDOM: [{ tag: 'em' }],
      toDOM: () => ['em', 0],
    },
  },
});
```

### 🎨 Live Cursors Implementation 
```TypeScript
interface CursorState {
  userId: string;
  userName: string;
  color: string;
  selection: { from: number; to: number };
}

function renderCursors(awareness: Awareness, editor: Editor) {
  const cursors: CursorState[] = [];
  
  awareness.getStates().forEach((state, clientId) => {
    if (clientId === awareness.clientID) return; // Skip self
    
    const user = state.user;
    const selection = state.selection;
    
    if (user && selection) {
      cursors.push({
        userId: clientId.toString(),
        userName: user.name,
        color: user.color,
        selection,
      });
    }
  });

  // Render cursor decorations in editor
  cursors.forEach(cursor => {
    const cursorEl = document.createElement('span');
    cursorEl.style.borderLeft = `2px solid ${cursor.color}`;
    cursorEl.style.position = 'absolute';
    cursorEl.dataset.userId = cursor.userId;
    
    const nameTag = document.createElement('span');
    nameTag.textContent = cursor.userName;
    nameTag.style.backgroundColor = cursor.color;
    nameTag.style.color = 'white';
    nameTag.style.padding = '2px 4px';
    nameTag.style.fontSize = '12px';
    nameTag.style.borderRadius = '3px';
    
    cursorEl.appendChild(nameTag);
    // Position cursor at selection.from
  });
}

```

### 🔄 Conflict Resolution Example (CRDT) 
```TypeScript
// Yjs automatically handles conflicts with CRDTs
// No manual conflict resolution needed!

import * as Y from 'yjs';

const doc1 = new Y.Doc();
const doc2 = new Y.Doc();

const text1 = doc1.getText('shared');
const text2 = doc2.getText('shared');

// User 1 inserts "Hello"
text1.insert(0, 'Hello');

// User 2 inserts "World" (offline, no sync yet)
text2.insert(0, 'World');

// Sync documents
const state1 = Y.encodeStateAsUpdate(doc1);
const state2 = Y.encodeStateAsUpdate(doc2);

Y.applyUpdate(doc1, state2);
Y.applyUpdate(doc2, state1);

// Both documents now have the same state (conflict-free!)
console.log(text1.toString()); // "HelloWorld" or "WorldHello" (deterministic)
console.log(text2.toString()); // Same as text1
```

### 📊 Version History Implementation 
```TypeScript
interface DocumentVersion {
  id: string;
  timestamp: Date;
  userId: string;
  snapshot: Uint8Array; // Yjs state vector
  changes: string; // Human-readable summary
}

class VersionHistory {
  private versions: DocumentVersion[] = [];

  saveVersion(ydoc: Y.Doc, userId: string, changes: string) {
    const snapshot = Y.encodeStateAsUpdate(ydoc);
    
    const version: DocumentVersion = {
      id: crypto.randomUUID(),
      timestamp: new Date(),
      userId,
      snapshot,
      changes,
    };

    this.versions.push(version);
  }

  restoreVersion(ydoc: Y.Doc, versionId: string) {
    const version = this.versions.find(v => v.id === versionId);
    if (!version) throw new Error('Version not found');

    // Clear current document
    const currentState = Y.encodeStateAsUpdate(ydoc);
    Y.applyUpdate(ydoc, Y.encodeStateAsUpdate(new Y.Doc()));

    // Apply snapshot
    Y.applyUpdate(ydoc, version.snapshot);
  }

  getVersionDiff(fromId: string, toId: string): Diff {
    // Calculate diff between two versions
    const from = this.versions.find(v => v.id === fromId);
    const to = this.versions.find(v => v.id === toId);
    
    // Use Yjs diff algorithm or custom implementation
    return calculateDiff(from!.snapshot, to!.snapshot);
  }
}

```

### 🌐 WebSocket Server Example (Yjs) 
```TypeScript
// server.ts
import { WebSocketServer } from 'ws';
import * as Y from 'yjs';
import { setupWSConnection } from 'y-websocket/bin/utils';

const wss = new WebSocketServer({ port: 1234 });

const docs = new Map<string, Y.Doc>();

wss.on('connection', (ws, req) => {
  const docName = new URL(req.url!, 'ws://localhost').searchParams.get('room');
  
  if (!docName) {
    ws.close();
    return;
  }

  // Get or create document
  if (!docs.has(docName)) {
    docs.set(docName, new Y.Doc());
  }

  const doc = docs.get(docName)!;

  setupWSConnection(ws, req, { docName, gc: true });

  console.log(`Client connected to room: ${docName}`);
});

console.log('WebSocket server running on ws://localhost:1234');
⚡ Performance Optimization Tips
TypeScript

// 1. Throttle updates to reduce network traffic
import { throttle } from 'lodash';

const sendUpdate = throttle((update) => {
  ws.send(update);
}, 50); // Send max every 50ms

// 2. Compress updates
import { compress, decompress } from 'lz4';

const compressedUpdate = compress(Y.encodeStateAsUpdate(doc));

// 3. Lazy load document history
async function loadDocument(docId: string) {
  const snapshot = await db.getLatestSnapshot(docId);
  const doc = new Y.Doc();
  Y.applyUpdate(doc, snapshot);
  
  // Load incremental updates since snapshot
  const updates = await db.getUpdatesSince(snapshot.timestamp);
  updates.forEach(update => Y.applyUpdate(doc, update));
  
  return doc;
}
```
