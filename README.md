# Next.js Nixpacks Boilerplate

A modern Next.js boilerplate project pre-configured with [Nixpacks](https://nixpacks.com/) for containerization and deployment. This template provides a solid foundation for building Next.js applications with Docker support and CI/CD integration.

## Features

- **Next.js 16** - Latest version of Next.js with App Router
- **React 19** - Latest React features and improvements
- **TypeScript** - Full TypeScript support
- **Tailwind CSS v4** - Modern utility-first CSS framework
- **Bun** - Fast package manager and runtime
- **Nixpacks** - Automatic containerization configuration
- **GitHub Actions** - CI/CD pipeline for building Docker images
- **Node.js 24** - Latest LTS Node.js version

## Tech Stack

- **Framework**: Next.js 16.0.7
- **Runtime**: React 19.2.0
- **Language**: TypeScript 5
- **Styling**: Tailwind CSS v4
- **Package Manager**: Bun
- **Containerization**: Nixpacks
- **Node Version**: 24.x

## Getting Started

### Prerequisites

- [Bun](https://bun.sh/) installed (or Node.js 24+ with npm/yarn/pnpm)
- Git

### Installation

1. Clone the repository:
```bash
git clone https://github.com/0xnithi/nextjs-nixpacks-boilerplate.git
cd nextjs-nixpacks-boilerplate
```

2. Install dependencies:
```bash
bun install
```

3. Run the development server:
```bash
bun dev
```

4. Open [http://localhost:3000](http://localhost:3000) in your browser.

## Development

### Available Scripts

- `bun dev` - Start development server
- `bun build` - Build for production
- `bun start` - Start production server
- `bun lint` - Run ESLint

### Project Structure

```
├── app/              # Next.js App Router directory
│   ├── layout.tsx   # Root layout
│   ├── page.tsx     # Home page
│   └── globals.css  # Global styles
├── public/          # Static assets
├── .github/         # GitHub Actions workflows
│   └── workflows/
│       └── nixpacks.yml  # CI/CD pipeline
├── nixpacks.toml    # Nixpacks configuration
├── next.config.ts   # Next.js configuration
└── package.json     # Dependencies and scripts
```

## Deployment

### Using Nixpacks

This project is configured with Nixpacks for automatic containerization. The `nixpacks.toml` file specifies Node.js 24 as the provider.

### GitHub Actions CI/CD

The project includes a GitHub Actions workflow (`.github/workflows/nixpacks.yml`) that:
- Builds Docker images using Nixpacks
- Pushes images to GitHub Container Registry (ghcr.io)
- Runs on push and pull requests to the `main` branch

To use the CI/CD pipeline:
1. Ensure your repository has GitHub Actions enabled
2. The workflow will automatically build and push images to `ghcr.io/0xnithi/nextjs-nixpacks-boilerplate:latest`
3. Update the image tag in the workflow file if needed

### Manual Docker Build

You can also build Docker images manually using Nixpacks:

```bash
nixpacks build . -o nextjs-app
```

## Configuration

### Nixpacks

The `nixpacks.toml` file configures the build environment:
- Uses Node.js 24 provider
- Automatically detects and installs dependencies

### Next.js

The `next.config.ts` file contains Next.js configuration. Customize it according to your needs.

## Learn More

- [Next.js Documentation](https://nextjs.org/docs) - Learn about Next.js features and API
- [Nixpacks Documentation](https://nixpacks.com/docs) - Learn about Nixpacks containerization
- [Bun Documentation](https://bun.sh/docs) - Learn about Bun runtime and package manager
- [Tailwind CSS Documentation](https://tailwindcss.com/docs) - Learn about Tailwind CSS

## License

See the [LICENSE](LICENSE) file for details.
