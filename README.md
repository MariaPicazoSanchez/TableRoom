# TableRoom

A web platform to play board games online with friends in real time.

## Games

- **UNO** — the classic multiplayer card game
- **Connect 4** — with AI bot (minimax + alpha-beta pruning)
- **Checkers** — with AI bot (minimax + alpha-beta pruning)

## Features

- Local and Google authentication (OAuth 2.0 + One-Tap)
- Email verification and password reset
- Real-time multiplayer gameplay via WebSocket (Socket.io)
- AI opponents for solo play
- Room and lobby management
- Responsive interface

## Tech Stack

| Layer | Technologies |
|-------|-------------|
| Backend | Node.js, Express 5, Socket.io, Passport.js |
| Database | MongoDB |
| Frontend | HTML5, Vanilla JS, React 19 + Vite |
| Auth | Passport Local, Google OAuth 2.0, Google One-Tap |
| Email | Nodemailer, Brevo API |
| Testing | Vitest, Supertest, Jasmine, Playwright |
| Infra | Google Cloud Secret Manager, Cloud Run |

## Installation

### Requirements

- Node.js >= 18
- MongoDB (local or Atlas)
- Google Cloud account (for OAuth and Secret Manager)
- Brevo account (for emails)

### Setup

```bash
# 1. Clone the repository
git clone https://github.com/MariaPicazoSanchez/TableRoom.git
cd TableRoom

# 2. Install server dependencies
npm install
cd server && npm install && cd ..

# 3. Install client dependencies
cd client && npm install && cd ..

# 4. Build game modules (React/Vite)
npm run build

# 5. Configure environment variables
cp .env.example .env
# Edit .env with your credentials
```

### Environment Variables

Create a `.env` file in the root with:

```env
MONGODB_URI=mongodb://localhost:27017/tableroom
SESSION_SECRET=your_session_secret
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
BREVO_API_KEY=your_brevo_api_key
BASE_URL=http://localhost:3000
```

### Running

```bash
# Development
npm run dev

# Production
npm start
```

The app will be available at `http://localhost:3000`.

## Tests

```bash
# Server tests (Vitest + Supertest)
npm test

# Server and client tests
npm run test:all

# End-to-end tests (Playwright)
npm run test:playwright
```

> 255 tests total: 202 server tests and 53 client tests.

## Project Structure

```
TableRoom/
├── index.js              # Entry point
├── server/
│   ├── src/              # Express app
│   ├── game/             # Game engines and AI bots
│   ├── cad.js            # Data access layer (MongoDB)
│   ├── modelo.js         # Business logic
│   ├── servidorWS.js     # WebSocket server
│   ├── email.js          # Email service
│   └── test/             # Server tests
├── client/
│   ├── *.html            # Pages
│   ├── js files/         # Client logic
│   ├── css/              # Styles
│   └── games/            # React modules (uno, connect4, checkers)
└── e2e/                  # Playwright end-to-end tests
```

## License

MIT — María Picazo Sánchez
