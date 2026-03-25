# TableRoom

A web platform to play board games online with friends in real time.

## Games

### Última Carta
A card game inspired by UNO with custom rules. Goal: be the first to empty your hand.

**Valid plays:** same color or same value as the top card, or a wildcard.

| Card | Effect |
|------|--------|
| Numbers 0–9 | Available in 4 colors (red, green, blue, yellow) |
| +2 | Next player draws 2 cards and loses their turn |
| +6 / +8 | Next player draws 6 or 8 cards |
| Skip | Next player loses their turn |
| Reverse | Reverses the play direction |
| Double | Next player draws cards equal to their current hand size |
| Wild | Changes the current color |
| +4 (wildcard) | Next player draws 4 cards, you choose the new color |
| Swap (wildcard) | Swap your entire hand with another player |
| Discard All (wildcard) | Discard all cards of a chosen color |

- **Última Carta:** when you have 1 card left, press the **Última Carta** button.
- **Hand limit:** if a player reaches 40 cards, they lose — the player with the fewest cards wins.
- **Forced draw:** if you have no playable card, you must draw. If you cannot draw, you lose your turn.

### Connect 4
Align 4 pieces horizontally, vertically, or diagonally. Includes AI bot (minimax + alpha-beta pruning).

### Checkers
Capture all opponent pieces or leave them with no moves. Mandatory captures. Pieces reaching the opposite edge are crowned **Queen (K)**. Includes AI bot (minimax + alpha-beta pruning).

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
