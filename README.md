# IDR to USD Spectrum (Audio Visualizer)

A beautiful web-based audio visualization tool that mimics a financial chart (USD/IDR exchange rate). You can upload your own audio files, play local tracks, or paste a YouTube URL to visualize it in real-time.

This project is a customization of the original `spectrum-idr` by [schzophree](https://github.com/schzophree) (Moonchi Kue Mochi), pre-configured to load a default song on startup.

## Features

- **Interactive Audio Visualizer**: Frequency domain visualizations (BASS, MID, FULL, WAVE, MAKS modes) that look like a financial stock chart.
- **YouTube Streaming Support**: Direct streaming and visualization of YouTube video tracks via a cloud-based server.
- **Local File Support**: Drag and drop or browse local files (MP3, WAV, FLAC, OGG, AAC) to play and visualize.
- **Custom Default Song**: Automatically loads the song from `https://youtu.be/RxzBHZ7KCzg` on startup.
- **Responsive Design**: Elegant dark-themed user interface optimized for mobile and desktop screens.
- **Autoplay Handling**: Gracefully handles browser autoplay policies by displaying a prompt until you click the Play button.

## How to Run Locally

Because the Web Audio API requires a secure context (local server) to process audio data, you cannot simply double-click the `index.html` file to run it. You need to run a local web server.

### Option 1: Using Node.js (Recommended)
If you have Node.js installed, open your terminal in this directory and run:
```bash
npx http-server -p 3000
```
Then open your browser and navigate to `http://localhost:3000`.

### Option 2: Live Server Extension (VS Code)
If you are using VS Code, install the **Live Server** extension, open the project folder, and click the **Go Live** button at the bottom right corner of VS Code.

---

## How to Deploy to Vercel (100% Free)

Yes, you can deploy this website to **Vercel** completely for free using Vercel's **Hobby Tier**! Vercel allows hosting static websites at no cost with zero configuration.

Here are the two ways to deploy it:

### Method A: Using GitHub (Recommended & Easiest)

1. **Create a GitHub Repository**:
   - Go to [GitHub](https://github.com/) and create a new public or private repository named `spectrum-idr`.
   - Upload/push these 4 files (`index.html`, `style.css`, `app.js`, `icon.ico`) to your new repository.

2. **Connect to Vercel**:
   - Sign up or log in at [Vercel](https://vercel.com/) (select **Hobby/Free** tier).
   - Click the **"Add New..."** button and select **"Project"**.
   - Import your GitHub repository.
   - Vercel will auto-detect it as a static website. Leave all settings at default and click **"Deploy"**.
   - Within seconds, your site will be live on a free `your-project-name.vercel.app` URL! Any future updates you push to GitHub will automatically redeploy.

### Method B: Using Vercel CLI (Without GitHub)

If you don't want to use GitHub, you can deploy directly from your command line:

1. **Install Vercel CLI**:
   Open terminal and run:
   ```bash
   npm install -g vercel
   ```
2. **Log In**:
   ```bash
   vercel login
   ```
   Follow the prompt to log in via your browser.
3. **Deploy**:
   In your project folder (`SPECTRUM`), run:
   ```bash
   vercel
   ```
   - Link to a new project: **Yes**
   - Project name: `spectrum-idr` (or your custom name)
   - Directory: `./`
   - Modify settings: **No**
4. Once completed, your project will have a preview deployment link. To push it to production (and get a clean permanent link), run:
   ```bash
   vercel --prod
   ```

---

## Technical Details

- **Frontend**: Vanilla HTML5, CSS3, ES6 JavaScript.
- **Audio Context**: Web Audio API `AudioContext`, `AnalyserNode` for frequency data.
- **Canvas API**: Custom high-performance rendering loop for drawing grid lines and spectrum curves.
- **Proxy Backend**: Streams YouTube video formats to standard PCM audio stream using the public Hugging Face Space endpoint (`https://schzophree-spectrum-idr-backend.hf.space`).
