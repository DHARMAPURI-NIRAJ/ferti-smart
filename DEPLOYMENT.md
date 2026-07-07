# Deployment Guide

This project is ready for deployment with:
- Backend: Render
- Frontend: Vercel

## 1. Push the repo to GitHub
Push the project to a GitHub repository.

## 2. Deploy the backend on Render
1. Open Render and create a new Web Service.
2. Connect your GitHub repository.
3. Set the root directory to `Backend`.
4. Build command:
   ```bash
   pip install -r requirements.txt
   ```
5. Start command:
   ```bash
   gunicorn main:app
   ```
6. Add environment variables:
   - `SUPABASE_URL`
   - `SUPABASE_ANON_KEY`
   - `GROQ_API_KEY` (optional)
   - `FLASK_DEBUG=False`
   - `PORT=10000`

Render will generate a public backend URL.

## 3. Deploy the frontend on Vercel
1. Open Vercel and create a new project.
2. Import the GitHub repository.
3. Set the root directory to `Frontend`.
4. Build command:
   ```bash
   npm run build
   ```
5. Add environment variable:
   - `VITE_API_URL=https://your-render-backend-url.onrender.com`

## 4. Test the live site
Open the Vercel URL and verify:
- the landing page loads
- AI features call the backend successfully
- optional Supabase/Groq features work if credentials are configured
