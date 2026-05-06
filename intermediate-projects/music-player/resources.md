# Resources for Music Player Application

## 📺 Video Tutorials
- [Build a Music Player with React & Howler.js](https://www.youtube.com/watch?v=QvWNEa_vS-s) - Web Dev Simplified: Complete tutorial (updated 2025)
- [Spotify Clone with Next.js 15, Tailwind & Howler.js](https://www.youtube.com/watch?v=3xrko3GpYoU) - Code with Antonio: Full implementation
- [Audio Visualization with Web Audio API & Canvas](https://www.youtube.com/watch?v=3NgVlAscdcA) - Web Audio API tutorial
- [Modern Music Player UI with Framer Motion](https://www.youtube.com/watch?v=QvWNEa_vS-s) - Beautiful UI design and animations

## 📚 Written Tutorials
- [Build a Music Player with React & Howler.js](https://www.freecodecamp.org/news/how-to-build-a-music-player/) - freeCodeCamp guide (2025 edition)
- [Web Audio API Guide](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API) - MDN documentation
- [Howler.js Tutorial](https://github.com/goldfire/howler.js#documentation) - Audio library guide
- [Audio Visualization with Canvas & Web Audio API](https://css-tricks.com/making-an-audio-waveform-visualizer-with-vanilla-javascript/) - CSS-Tricks tutorial

## 🔧 Tools & Libraries

### Audio Playback
- [Howler.js](https://howlerjs.com/) - Audio library for the web - **RECOMMENDED**
- [Tone.js](https://tonejs.github.io/) - Web Audio framework
- [Wavesurfer.js](https://wavesurfer-js.org/) - Waveform visualizer
- [React Player](https://github.com/cookpete/react-player) - React audio/video component

### Audio Visualization
- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) - Browser audio API
- [Wavesurfer.js](https://wavesurfer-js.org/) - Audio waveform visualizer
- [p5.js](https://p5js.org/) - Creative coding library (for custom visualizations)
- [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) - For custom visualizations

### State Management
- [Zustand](https://github.com/pmndrs/zustand) - Lightweight state management
- [Redux Toolkit](https://redux-toolkit.js.org/) - Complex state management
- [Jotai](https://jotai.org/) - Atomic state management

### UI Components
- [Framer Motion](https://www.framer.com/motion/) - Animation library
- [React Spring](https://www.react-spring.dev/) - Spring physics animations
- [Radix UI](https://www.radix-ui.com/) - Accessible components (sliders, etc.)

## 💻 GitHub Repositories
- [Spotify Clone with Next.js 16](https://github.com/adrianhajdin/project_spotify_clone) - Complete implementation
- [Music Player with Howler.js](https://github.com/bradtraversy/music-player) - Vanilla JS example
- [Apple Music Clone](https://github.com/topics/music-player) - Various implementations
- [Nuclear Music Player](https://github.com/nukeop/nuclear) - Open-source desktop player (Electron)

## 📖 Learning Resources

### Audio Fundamentals
- [Web Audio API Tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) - MDN comprehensive guide
- [Understanding Audio](https://web.dev/audio-output-latency/) - Web.dev audio guide
- [Audio Buffering](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/buffered) - Buffering explained

### Visualization
- [Audio Visualization Guide](https://www.sitepoint.com/how-to-build-a-music-visualizer/) - Complete tutorial
- [Canvas Tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial) - Canvas basics
- [Analyser Node](https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode) - Web Audio analyzer

### Music APIs
- [Spotify Web API](https://developer.spotify.com/documentation/web-api) - Reference (requires premium)
- [Last.fm API](https://www.last.fm/api) - Music metadata and scrobbling
- [Musixmatch API](https://developer.musixmatch.com/) - Lyrics database
- [Genius API](https://docs.genius.com/) - Lyrics and annotations

## 🌐 APIs & Services
- [Spotify Web API](https://developer.spotify.com/documentation/web-api) - Music streaming API
- [Deezer API](https://developers.deezer.com/api) - Alternative music API
- [Last.fm API](https://www.last.fm/api) - Music metadata (free)
- [Musixmatch API](https://developer.musixmatch.com/) - Lyrics (14-day trial)
- [YouTube Music API](https://developers.google.com/youtube/v3) - YouTube integration

## 🎨 Design Resources
- [Spotify Design](https://www.spotify.com/design/) - Official design system
- [Apple Music UI](https://music.apple.com/) - Design inspiration
- [Dribbble Music Players](https://dribbble.com/search/music-player) - UI designs
- [Figma Music Player Templates](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=music+player) - Free templates

## 📚 Audio Player Component Example
```tsx
import { useRef, useState, useEffect } from 'react';
import { Howl } from 'howler';

export function AudioPlayer({ track }) {
  const [isPlaying, setIsPlaying] = useState(false);
  const [progress, setProgress] = useState(0);
  const [volume, setVolume] = useState(1);
  const soundRef = useRef<Howl | null>(null);

  useEffect(() => {
    soundRef.current = new Howl({
      src: [track.audioUrl],
      html5: true,
      onplay: () => setIsPlaying(true),
      onpause: () => setIsPlaying(false),
      onend: () => {
        setIsPlaying(false);
        setProgress(0);
      },
    });

    return () => {
      soundRef.current?.unload();
    };
  }, [track]);

  useEffect(() => {
    if (!soundRef.current) return;

    const interval = setInterval(() => {
      if (soundRef.current?.playing()) {
        const seek = soundRef.current.seek();
        const duration = soundRef.current.duration();
        setProgress((seek / duration) * 100);
      }
    }, 100);

    return () => clearInterval(interval);
  }, []);

  const togglePlay = () => {
    if (isPlaying) {
      soundRef.current?.pause();
    } else {
      soundRef.current?.play();
    }
  };

  const handleSeek = (e: React.ChangeEvent<HTMLInputElement>) => {
    const duration = soundRef.current?.duration() || 0;
    const seekTo = (parseFloat(e.target.value) / 100) * duration;
    soundRef.current?.seek(seekTo);
    setProgress(parseFloat(e.target.value));
  };

  const handleVolumeChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    const vol = parseFloat(e.target.value);
    setVolume(vol);
    soundRef.current?.volume(vol);
  };

  return (
    <div className="audio-player">
      <div className="track-info">
        <img src={track.albumArt} alt={track.title} />
        <div>
          <h3>{track.title}</h3>
          <p>{track.artist}</p>
        </div>
      </div>

      <div className="controls">
        <button onClick={togglePlay}>
          {isPlaying ? '⏸️' : '▶️'}
        </button>
      </div>

      <input
        type="range"
        min="0"
        max="100"
        value={progress}
        onChange={handleSeek}
        className="progress-bar"
      />

      <input
        type="range"
        min="0"
        max="1"
        step="0.01"
        value={volume}
        onChange={handleVolumeChange}
        className="volume-slider"
      />
    </div>
  );
}