
# Realm Explorers - Multiplayer Game

## Local Development

To run the game locally:

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd realm-explorers
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

4. Open http://localhost:8080 in your browser to play the game.

## Deployment Instructions

### Deploy the Client (Frontend)

The frontend can be deployed to any static site hosting service. Here are instructions for a few popular options:

#### Deploy to Netlify

1. Push your code to GitHub
2. Sign up for a Netlify account if you don't have one
3. Click "New site from Git"
4. Select your GitHub repository
5. Set build command as: `npm run build`
6. Set publish directory as: `dist`
7. Click "Deploy site"

#### Deploy to Vercel

1. Push your code to GitHub
2. Sign up for Vercel account if you don't have one
3. Click "Import Project"
4. Select your GitHub repository
5. The build settings should be automatically detected
6. Click "Deploy"

### Running Your Own Multiplayer Server

For a complete multiplayer experience, you'll need to set up a server. 

1. Check out the server repository: [https://github.com/yourusername/realm-explorers-server](https://github.com/yourusername/realm-explorers-server)

2. Follow the instructions in the server repository to deploy your own server instance.

3. Once your server is deployed, update the `VITE_SOCKET_SERVER_URL` environment variable in your client deployment to point to your server:

   For example, in Netlify:
   - Go to Site settings > Environment variables
   - Add a new variable: `VITE_SOCKET_SERVER_URL` with the value of your server URL
   - Redeploy your site

## Saving Game State

The game currently doesn't have persistent game state. All player positions and messages are stored in memory and lost when you refresh the page or disconnect.

To implement game state saving:
1. You would need to extend the server to store player positions in a database
2. Add authentication to identify players between sessions
3. Add API endpoints to save and retrieve game progress
