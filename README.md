# Counter App with Context API

## Project Overview
This project demonstrates a counter application using Next.js and React, implementing the Context API for global state management.

## Features
- Global state management with Context API
- Shared counter state across components
- Dynamic header display based on route
- Persistent counter state throughout the application

## Technical Implementation

### Directory Structure
```
alx-project-0x05/
├── context/
│   └── CountContext.tsx
├── pages/
│   ├── _app.tsx
│   └── counter-app.tsx
├── components/
│   └── layouts/
│       ├── Layout.tsx
│       └── Header.tsx
└── styles/
    └── globals.css
```

### Key Components

#### Context Provider (`context/CountContext.tsx`)
```typescript
interface CountContextProps {
  count: number;
  increment: () => void;
  decrement: () => void;
}

export const CountProvider = ({ children }: { children: ReactNode}) => {
  const [count, setCount] = useState<number>(0);
  ...
}
```

#### App Wrapper (`pages/_app.tsx`)
```typescript
export default function App({ Component, pageProps }: AppProps) {
  return (
    <CountProvider>
      <Layout>
        <Component {...pageProps} />
      </Layout>
    </CountProvider>
  )
}
```

## Technical Notes
- Implements React Context API
- TypeScript for type safety
- Shared state between Header and Counter components
- Dynamic UI based on current route
