# What's This?

Using this module, you can ask GPT-4 Turbo.

# Develop

### Create Commit Message Automatically and Push It Straight Away

When you want to commit changes, you can also use GPT-4 Turbo through Clarifai. You need to set the environment variable `CLARIFAI_API_KEY`. Go to [https://clarifai.com/settings/security](https://clarifai.com/settings/security), and copy and paste your personal access token there. Then run:

```
pnpm run commit-clarifai
```

You can also use a less powerful AI, Gemini Pro by Google, but be aware that because it's a free version, Google will use all your input for training data. To use Gemini Pro to create a commit, you need to set `GOOGLE_API_KEY`. You can obtain the API key here: [https://makersuite.google.com](https://makersuite.google.com). In `packages/scripts`, see `.env.example`, then change the filename to `.env`. After you've done that, you can use it by running:

```
pnpm run commit
```

### Auto Fix `README.md` Grammar

You can easily fix grammar in this `README.md` using the power of Clarifai GPT-4 Turbo by running `pnpm run fix-grammar`. And if you want to fix grammar and create a commit message automatically and push it straight away, use the command `pnpm run fix-and-commit`.

### Some Notes

- If any commit message is in Indonesian languages, you can change the prompt in `packages/scripts/commit-clarifai.js`, especially the one saying:

```
Translate the commit <subject> and <body> to the Indonesian language. Here's an example of a good commit message:

---
✨ feat(README): tambah instruksi penggunaan Clarifai untuk pesan commit

Menambahkan bagian tentang penggunaan Clarifai untuk penerjemahan pesan commit yang lebih kuat ke dalam bahasa Indonesia. Pengguna harus menempatkan `CLARIFAI_API_KEY` di dalam file `.env` dan menjalankan perintah `pnpm run commit-clarifai`.
---
```