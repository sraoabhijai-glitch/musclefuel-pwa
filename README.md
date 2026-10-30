# MuscleFuel PWA

Static, offline-capable diet tracker. No build step, framework, database, or API keys required.

## Deploy to GitHub Pages
1. Create a public GitHub repository named `musclefuel-pwa`.
2. Upload **the contents of this folder** to the repository root, keeping the `icons` directory intact.
3. Go to **Settings → Pages → Build and deployment**.
4. Choose **Deploy from a branch**, select **main**, select **/(root)**, then **Save**.
5. Wait for the Pages deployment. Your address will be `https://YOUR-USERNAME.github.io/musclefuel-pwa/`.
6. On iPhone, open the URL in Safari → Share → Add to Home Screen → enable Open as Web App → Add.

## Local development
Run `python -m http.server 8000` from this directory and open `http://localhost:8000`. Service workers require localhost or HTTPS, not `file://`.

## Data & nutrition
Data is stored in browser localStorage on the device. Export JSON backups regularly in Settings. Installing on iOS can create separate storage from Safari. No account sync. Nutrition values are approximate reference values per 100 g/ml; real labels and cooking methods vary. The four-day grocery checklist is an initial template, not dynamically derived from meal edits. Supplement and kidney-stone advice is not individualized medical guidance.

## Updating
Edit files, commit to `main`, and GitHub Pages will republish. The service worker uses network-first caching for same-origin files, so online reloads can fetch updates.

## v1.1 — Detailed meal guidance
Meals now show all eight planned meals with preparation instructions, portion guidance, alternatives, and notes. The meal ingredient lists remain editable and drive nutrition totals. After uploading the new files to GitHub, reload the installed app while online to receive the update. Existing local tracking data is retained.


## Meal checklist update (v1.2)
- Tick individual foods in each meal; consumed nutrition updates per checked item.
- Use 'Mark entire meal complete' to tick all ingredients at once.
- Add an existing food with a quantity, or create a custom food by entering nutrition per 100 g/ml.
- Individual food checkmarks are tracked by date. Planned ingredient quantity edits apply to the meal plan across dates.
- When updating GitHub Pages, upload the contents of this folder and commit. The service worker cache version is bumped so clients can receive the updated files.

## v1.3 meal editor and reminders

Open Settings to edit meal names, times, descriptions, instructions, alternatives, and nutrition targets. Add/delete meals there; manage each meal's food items in the Meals tab.

Notification reminders are supported only while the app is actively running. **Background Web Push is not yet implemented**; see `NOTIFICATIONS.md` for iPhone limitations and required backend infrastructure.
