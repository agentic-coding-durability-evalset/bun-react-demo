# Bun React Demo

A full-stack application demo project based on [Bun](https://bun.sh/) and [React](https://react.dev/). Demonstrates how to use Bun as a runtime, build tool, and package manager to build modern React applications.

## Tech Stack

- **Bun**: Latest version (JavaScript runtime and toolchain)
- **React**: 19.2
- **React DOM**: 19.2
- **Tailwind CSS**: 4.1.11
- **TypeScript**: Supported

## Project Structure

```
bun-react-demo/
├── src/
│   ├── index.ts         # Server entry point, API routes and static file serving
│   ├── index.html       # HTML template
│   ├── App.tsx          # Main React component
│   ├── frontend.tsx     # Frontend entry point
│   ├── APITester.tsx    # API testing component
│   ├── index.css        # Global styles
│   └── logo.svg         # Asset file
├── build.ts             # Build script
├── package.json         # Project dependency configuration
├── tsconfig.json        # TypeScript configuration
├── bunfig.toml          # Bun configuration file
└── README.md
```

## Features

- Full-stack application (frontend + backend)
- React 19 support
- Tailwind CSS styling
- Hot Module Replacement (HMR)
- API route handling
- Static file serving
- TypeScript support

## Quick Start

### Prerequisites

- [Bun](https://bun.sh/) latest version

### Installation and Running

```bash
# Install dependencies (Bun handles this automatically)
bun install

# Run development server
bun run dev
```

The application will start at `http://localhost:3000` with hot reload support.
Note: Port 3000 is Bun's default port.

### Production Build

```bash
# Build project
bun run build

# Run production version
bun run start
```

## API Endpoints

### Hello API
```http
GET http://localhost:3000/api/hello
PUT http://localhost:3000/api/hello
```
Response example:
```json
{
  "message": "Hello, world!",
  "method": "GET"
}
```

### Parameterized Hello API
```http
GET http://localhost:3000/api/hello/:name
```
Response example:
```json
{
  "message": "Hello, Alice!"
}
```

## Code Description

### Server (`src/index.ts`)

Bun server configuration:
- **Static file serving**: All unmatched routes return `index.html` (supports React Router)
- **API routes**: `/api/hello` and `/api/hello/:name`
- **Development mode**: Enables HMR and browser console logging

### React Application (`src/App.tsx`)

Main React component:
- Displays Bun and React logos
- Includes API testing component
- Uses Tailwind CSS for styling

### API Testing Component (`src/APITester.tsx`)

Interactive component for testing the backend API.

## Development Features

### Hot Module Replacement (HMR)

In development mode, code changes automatically refresh the browser without manual refresh.

### TypeScript Support

The project is fully written in TypeScript, providing type safety.

### Tailwind CSS

Uses Tailwind CSS 4.x for styling with JIT compilation support.

## Build and Deployment

### Building

```bash
bun run build
```

The build script will:
- Compile TypeScript
- Process React components
- Optimize asset files
- Generate production-ready build

### Environment Variables

Can be configured via environment variables:
- `NODE_ENV`: Set to `production` to disable development features

## References

- [Bun Official Website](https://bun.sh/)
- [React Documentation](https://react.dev/)
- [Tailwind CSS Documentation](https://tailwindcss.com/)
