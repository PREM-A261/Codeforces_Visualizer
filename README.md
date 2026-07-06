# 🏆 Codeforces Visualizer

A simple React web app that lets you look up any [Codeforces](https://codeforces.com) handle and instantly see a clean summary of that user's competitive programming profile — rating, rank, best contest performance, last solved problem, and a tag-wise breakdown of every problem they've solved.

![React](https://img.shields.io/badge/React-18.3.1-61DAFB?logo=react&logoColor=white)
![Parcel](https://img.shields.io/badge/Bundler-Parcel-e9a337)
![License](https://img.shields.io/badge/license-ISC-blue)

---

## ✨ Features

- 🔍 **Search any Codeforces handle** and fetch their public profile data
- 🧑‍💻 **Profile summary** — name, location, college/organization, current & max rating/rank
- 🏅 **Best contest rank** achieved across all rated contests
- 📌 **Last problem solved**, with a direct link to it on Codeforces
- 🏷️ **Tag-wise breakdown** of the total number of unique problems solved, grouped by topic/tag
- 💀 **Shimmer/skeleton loading state** while data is being fetched
- ⚡ Built with plain React (function components + hooks) and bundled with Parcel — no heavy framework overhead

## 🖥️ Demo

Enter a Codeforces handle (e.g. `tourist`, `Errichto`) in the search bar and click **Search** to see their stats rendered on the page.

## 🧱 Tech Stack

| Layer      | Technology                     |
|------------|---------------------------------|
| UI Library | React 18 (Hooks: `useState`, `useEffect`) |
| Bundler    | Parcel 1.x                      |
| Styling    | Plain CSS (`style.css`)         |
| Data Source| [Codeforces public API](https://codeforces.com/apiHelp) |

## 📂 Project Structure

```
codeforces-visualizer/
├── index.html          # HTML entry point
├── index.js            # React root render + app entry
├── header.js            # Header component (title + nav)
├── Body.js              # Main component: search bar + data fetching + results
├── CartShimmer.js        # Skeleton/loading placeholder component
├── Footer.js             # Footer component
├── style.css             # Global styles
├── package.json           # Project metadata & scripts
└── dist/                  # Production build output (generated)
```

## 🔌 API Endpoints Used

This app talks directly to the public, keyless Codeforces API:

| Purpose                     | Endpoint |
|------------------------------|----------|
| User profile info            | `GET https://codeforces.com/api/user.info?handles={handle}` |
| Contest rating history       | `GET https://codeforces.com/api/user.rating?handle={handle}` |
| Submission history           | `GET https://codeforces.com/api/user.status?handle={handle}` |

No API key is required, and all requests are made client-side directly from the browser.

## 🚀 Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v14+ recommended)
- npm (comes with Node.js)

### Installation

```bash
# Clone the repository
https://github.com/PREM-A261/Codeforces_Visualizer.git
cd codeforces-visualizer

# Install dependencies
npm install
```

### Run locally

```bash
npm start
```

This runs `parcel index.html --open`, which starts a dev server (default: `http://localhost:1234`) and opens the app in your browser.

### Build for production

```bash
npx parcel build index.html
```

The optimized static output is generated in the `dist/` folder, ready to be deployed to any static hosting provider (Vercel, Netlify, GitHub Pages, etc.).

## ☁️ Deployment

This project builds to a fully static site, so it can be deployed anywhere that serves static files:

**Vercel**
1. Push this repo to GitHub.
2. Go to [vercel.com/new](https://vercel.com/new) and import the repository.
3. Set:
   - **Build Command:** `npx parcel build index.html`
   - **Output Directory:** `dist`
4. Click **Deploy**.

**Netlify** works the same way — build command `npx parcel build index.html`, publish directory `dist`.

## 🗺️ Roadmap / Ideas for Improvement

- [ ] Add loading/error states for invalid or non-existent handles
- [ ] Add a rating-over-time chart (e.g. using Chart.js or Recharts)
- [ ] Add dark mode
- [ ] Migrate build tooling from Parcel 1.x to Vite for faster builds
- [ ] Add unit tests (Jest is already listed as a dev dependency)

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
1. Fork the project
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the **ISC License**.

## 🙋 Author

Made with ❤️ by **Satyam**
