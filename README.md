# Meme Generator

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)

A fun React app that lets you generate memes by picking a random image from the Imgflip API and adding your own top and bottom text.

For testing guide look for in `testREADME.md`.

## Index

- [About](#about)
- [Usage](#usage)
- [Development](#development)
- [Contribution](#contribution)
- [License](#license)

---

## About

A small meme generator app built with React that fetches real meme templates from the Imgflip API. The main goal was to learn how to:

- Use `useState` to manage multiple pieces of state in a single component
- Use `useEffect` to fetch data from an external API on component mount
- Handle controlled inputs with a shared `handleChange` function using `event.currentTarget`
- Spread state updates to avoid overwriting unrelated fields
- Compose a React app across multiple components (`App`, `Header`, `Main`)
- Style overlaid text on images using absolute positioning and CSS `text-shadow`

---

## Usage

### Installation

1. Clone the repository: `git clone <your-repo-url>`
2. Navigate into the project folder: `cd meme-generator`
3. Install dependencies: `npm install`
4. Start the development server: `npm run dev`
5. Open your browser and go to `http://localhost:5173`

### Commands

I'm using Vite to make development faster. Here are the main scripts I use:
```
npm run dev     // Starts the project so I can see changes live.
npm run build   // Prepares the project for the real world (deployment).
npm run preview // Lets me check the build version locally.
```

---

## Development

### Pre-Requisites:
- Node.js (v16 or higher)
- A text editor (VS Code recommended)
- Basic knowledge of React and JavaScript

### File Structure

| No | File Name | What it does |
| --- | --------- | ------------ |
| 1 | `index.html` | Entry HTML file, mounts the React root |
| 2 | `index.jsx` | Bootstraps the React app into the DOM |
| 3 | `index.css` | Global styles for the layout, header, form, and meme display |
| 4 | `App.jsx` | Root component that composes `Header` and `Main` |
| 5 | `Header.jsx` | Renders the purple gradient header bar with logo and title |
| 6 | `Main.jsx` | Core logic — manages meme state, fetches images, handles input changes |

### Build

The app fetches a list of meme templates from the Imgflip public API when it first loads and stores them in state. When the user clicks **"Get a new meme image"**, a random template is selected from that list. The two text inputs are controlled components tied to the `meme` state object, so typing in either field instantly updates the overlay text rendered on top of the meme image.

---

## Contribution

1. Found a bug? Open an issue and I'll try to fix it.
2. Advice? If you have ideas for improving the meme customization experience (font size control, image download, color picker, etc.), let me know!

### Guideline

Keep changes focused and minimal. If you're adding a new feature, make sure it doesn't break the existing controlled input behaviour or the API fetch logic. Open a pull request with a short description of what you changed and why.

---

## License

Feel free to use this for your own practice! **MIT** License.
