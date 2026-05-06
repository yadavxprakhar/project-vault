# Resources for Video Streaming Platform

## 📺 Video Tutorials
- [Build a Video Streaming Platform with Next.js 15 & Mux](https://www.youtube.com/watch?v=5QlE6o-iYcE) - JavaScript Mastery: Complete tutorial (2025 edition)
- [YouTube Clone with Next.js 16, Prisma & Cloudflare Stream](https://www.youtube.com/watch?v=VaCoPGVWFP8) - Lama Dev: Full-stack implementation
- [Video Upload, Transcoding & Streaming with FFmpeg & Next.js](https://www.youtube.com/watch?v=8vrTMbxrVKo) - Web Dev Simplified: Upload and adaptive playback
- [FFmpeg Video Processing & HLS Streaming in 2026](https://www.youtube.com/watch?v=MPV7JXTWPWI) - FFmpeg tutorial for developers

## 📚 Written Tutorials
- [Build a Video Streaming App with Next.js 15 & Cloudflare](https://www.freecodecamp.org/news/how-to-build-a-video-streaming-app/) - freeCodeCamp guide (updated 2026)
- [HLS Streaming Guide with Cloudflare Stream](https://developers.cloudflare.com/stream/streaming-with-hls/) - Cloudflare HLS documentation
- [Video Processing with FFmpeg](https://www.ffmpeg.org/ffmpeg.html) - Official FFmpeg docs
- [Cloudflare Stream Tutorial](https://developers.cloudflare.com/stream/) - Managed video platform

## 🔧 Tools & Libraries

### Video Players
- [Video.js](https://videojs.com/) - Open-source HTML5 video player - **RECOMMENDED**
- [Plyr](https://plyr.io/) - Simple, accessible media player
- [React Player](https://github.com/cookpete/react-player) - React component for multiple sources
- [Shaka Player](https://github.com/shaka-project/shaka-player) - DASH and HLS support

### Video Processing
- [FFmpeg](https://www.ffmpeg.org/) - Complete video/audio processing - **ESSENTIAL**
- [fluent-ffmpeg](https://github.com/fluent-ffmpeg/node-fluent-ffmpeg) - FFmpeg wrapper for Node.js
- [HandBrake](https://handbrake.fr/) - Video transcoding (alternative)

### Video Storage & CDN
- [AWS S3](https://aws.amazon.com/s3/) - Scalable object storage
- [Cloudflare R2](https://www.cloudflare.com/products/r2/) - S3-compatible storage (no egress fees)
- [Bunny CDN](https://bunny.net/) - Affordable video CDN
- [Mux](https://www.mux.com/) - Managed video API (all-in-one solution)

### Live Streaming
- [WebRTC](https://webrtc.org/) - Real-time communication
- [LiveKit](https://livekit.io/) - Modern open-source WebRTC platform
- [OBS Studio](https://obsproject.com/) - Streaming software (for reference)
- [Agora](https://www.agora.io/) - Real-time engagement platform

## 💻 GitHub Repositories
- [YouTube Clone with Next.js 16](https://github.com/adrianhajdin/project_youtube_clone) - Complete implementation
- [Video Streaming App with Next.js & Cloudflare](https://github.com/bradtraversy/video-streaming-app) - Full-stack example
- [Video.js Examples](https://github.com/videojs/video.js/tree/main/docs/examples) - Official examples
- [PeerTube](https://github.com/Chocobozzz/PeerTube) - Decentralized video platform (reference)
- [Streamlabs OBS](https://github.com/stream-labs/streamlabs-obs) - Open-source streaming tools

## 📖 Learning Resources

### Video Streaming Fundamentals
- [HTTP Live Streaming (HLS)](https://developer.apple.com/streaming/) - Apple's HLS specification
- [DASH Streaming](https://dashif.org/guidelines/) - Dynamic Adaptive Streaming
- [Video Encoding Guide](https://www.encoding.com/blog/2021/05/19/video-encoding-101/) - Encoding basics
- [Bitrate vs Quality](https://www.adobe.com/creativecloud/video/discover/bitrate.html) - Understanding bitrates

### FFmpeg
- [FFmpeg Documentation](https://ffmpeg.org/documentation.html) - Official docs
- [FFmpeg Cheat Sheet](https://gist.github.com/steven2358/ba153c642fe2bb1e47485962df07c730) - Common commands
- [Video Transcoding](https://trac.ffmpeg.org/wiki/Encode/H.264) - H.264 encoding guide

### Performance Optimization
- [Video Optimization](https://web.dev/fast/#optimize-your-media) - Web.dev guide
- [CDN Best Practices](https://www.cloudflare.com/learning/cdn/cdn-best-practices/) - Cloudflare guide
- [Lazy Loading Videos](https://web.dev/lazy-loading-video/) - Performance tips

## 🌐 APIs & Services
- [Mux API](https://docs.mux.com/) - Video infrastructure (encoding, streaming, analytics)
- [Cloudflare Stream](https://developers.cloudflare.com/stream/) - Video platform API
- [AWS MediaConvert](https://aws.amazon.com/mediaconvert/) - Video transcoding service
- [YouTube Data API](https://developers.google.com/youtube/v3) - For reference/inspiration
- [Vimeo API](https://developer.vimeo.com/) - Alternative video platform API

## 🎨 Design Resources
- [YouTube Design](https://www.youtube.com/) - UI/UX reference
- [Twitch Design](https://www.twitch.tv/) - Live streaming UI
- [Netflix UI](https://www.netflix.com/) - Video browsing inspiration
- [Figma Video Player Templates](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=video+player) - Free templates

## 📚 Video Upload Example
```typescript
// Using Multer for file upload
import multer from 'multer';
import { S3Client, PutObjectCommand } from '@aws-sdk/client-s3';

const storage = multer.memoryStorage();
const upload = multer({ storage });

const s3Client = new S3Client({ region: 'us-east-1' });

app.post('/api/upload', upload.single('video'), async (req, res) => {
  try {
    const file = req.file;
    const key = `videos/${Date.now()}-${file.originalname}`;

    await s3Client.send(new PutObjectCommand({
      Bucket: process.env.S3_BUCKET,
      Key: key,
      Body: file.buffer,
      ContentType: file.mimetype,
    }));

    // Add to processing queue
    await videoQueue.add('transcode', {
      videoKey: key,
      userId: req.user.id,
    });

    res.json({ success: true, videoId: key });
  } catch (error) {
    res.status(500).json({ error: 'Upload failed' });
  }
});

### 🎬 FFmpeg Transcoding Example

// Using fluent-ffmpeg
const ffmpeg = require('fluent-ffmpeg');

async function transcodeVideo(inputPath, outputPath) {
  return new Promise((resolve, reject) => {
    ffmpeg(inputPath)
      .output(outputPath + '/360p.mp4')
      .videoCodec('libx264')
      .size('640x360')
      .videoBitrate('800k')
      .output(outputPath + '/720p.mp4')
      .videoCodec('libx264')
      .size('1280x720')
      .videoBitrate('2500k')
      .output(outputPath + '/1080p.mp4')
      .videoCodec('libx264')
      .size('1920x1080')
      .videoBitrate('5000k')
      .on('end', resolve)
      .on('error', reject)
      .run();
  });
}

### 📊 Database Schema Example

model Video {
  id          String    @id @default(cuid())
  title       String
  description String?
  duration    Int       // seconds
  thumbnail   String
  videoUrl    String    // Original upload
  qualities   Quality[] // Transcoded versions
  views       Int       @default(0)
  likes       Int       @default(0)
  dislikes    Int       @default(0)
  channelId   String
  channel     Channel   @relation(fields: [channelId], references: [id])
  comments    Comment[]
  playlists   Playlist[]
  category    String?
  tags        String[]
  published   Boolean   @default(false)
  publishedAt DateTime?
  createdAt   DateTime  @default(now())
  updatedAt   DateTime  @updatedAt
}

model Quality {
  id        String @id @default(cuid())
  videoId   String
  video     Video  @relation(fields: [videoId], references: [id])
  resolution String // 360p, 720p, 1080p
  url       String
  size      Int    // bytes
}

model Channel {
  id           String   @id @default(cuid())
  name         String
  handle       String   @unique
  description  String?
  avatar       String?
  banner       String?
  ownerId      String
  owner        User     @relation(fields: [ownerId], references: [id])
  videos       Video[]
  subscribers  Subscription[]
  subscriberCount Int   @default(0)
  createdAt    DateTime @default(now())
}

model Comment {
  id        String    @id @default(cuid())
  content   String
  videoId   String
  video     Video     @relation(fields: [videoId], references: [id])
  userId    String
  user      User      @relation(fields: [userId], references: [id])
  parentId  String?
  parent    Comment?  @relation("CommentReplies", fields: [parentId], references: [id])
  replies   Comment[] @relation("CommentReplies")
  likes     Int       @default(0)
  createdAt DateTime  @default(now())
}

model Subscription {
  id        String   @id @default(cuid())
  userId    String
  user      User     @relation(fields: [userId], references: [id])
  channelId String
  channel   Channel  @relation(fields: [channelId], references: [id])
  createdAt DateTime @default(now())

  @@unique([userId, channelId])
}

### 🎥 Video Player Component

import ReactPlayer from 'react-player';

export function VideoPlayer({ videoUrl, qualities }) {
  const [selectedQuality, setSelectedQuality] = useState('720p');

  const currentUrl = qualities.find(q => q.resolution === selectedQuality)?.url || videoUrl;

  return (
    <div className="video-player-wrapper">
      <ReactPlayer
        url={currentUrl}
        controls
        width="100%"
        height="100%"
        config={{
          file: {
            attributes: {
              controlsList: 'nodownload'
            }
          }
        }}
      />
      <div className="quality-selector">
        {qualities.map(q => (
          <button
            key={q.resolution}
            onClick={() => setSelectedQuality(q.resolution)}
            className={selectedQuality === q.resolution ? 'active' : ''}
          >
            {q.resolution}
          </button>
        ))}
      </div>
    </div>
  );
}