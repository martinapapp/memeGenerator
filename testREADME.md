# Meme Generator App TEST

## Prerequisites

- **Node.js** (v18 or higher recommended) 
- **npm**

Verify your versions by running:
```bash
node -v
npm -v
```

## Step 1 — Clone or Initialize the Project

If you're starting from an existing repo:
```bash
git clone <your-repo-url>
cd <project-folder>
```

## Step 2 — Install Core Dependencies

This installs everything listed in `package.json`, including React and Vite.
```bash
npm install
```

## Step 3 — Install Vitest and Testing Libraries

Your config uses `vitest`, `jsdom`, and Istanbul coverage, so install them:
```bash
npm install -D vitest @vitest/coverage-istanbul jsdom @testing-library/react @testing-library/jest-dom @testing-library/user-event msw@1.3.5
```

Here's what each package does:
- `vitest` — the test runner
- `@vitest/coverage-istanbul` — coverage provider specified in your config
- `jsdom` — simulates a browser DOM environment for tests
- `@testing-library/react` — utilities for rendering and querying React components
- `@testing-library/jest-dom` — adds custom matchers like `toBeInTheDocument()`
- `@testing-library/user-event` — simulates user interactions
- `msw@1.3.5` — mock service worker for intercepting and mocking API requests in tests

## Step 4 — The `test-setup.js` in the root should contain: 

```
import { defineConfig } from 'vite'
import { coverageConfigDefaults } from 'vitest/config'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  test: {
    setupFiles: ["./test-setup.js"],
    environment: 'jsdom',
    coverage: {
      provider: 'istanbul',
      exclude: ['./src/index.jsx', ...coverageConfigDefaults.exclude]
    }
  }
})
```

## Step 5 — Test Scripts in package.json

```json
"scripts": {
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview",
  "test": "vitest",
  "test:coverage": "vitest --coverage"
}
```

## Step 6 — Run the Dev Server

Your app will be available at `http://localhost:5173` by default.
```bash
npm run dev
```

## Step 7 — Run Tests

To run tests in watch mode:
```bash
npm run test
```

Coverage output will be generated in a `/coverage` folder.
To run tests once and generate a coverage report:
```bash
npm run test:coverage
```



