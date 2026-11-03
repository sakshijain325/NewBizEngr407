# Homeward

A pet-matching prototype for ENGR 407 (Product Innovation). People take a lifestyle quiz and get ranked dog and cat matches from vetted shelters and breeders. Each match explains why the animal fits and what to ask before meeting. Shelters get a dashboard of pre-screened inquiries ranked by fit.

> All animals, shelters, breeders and applicants in the prototype are fictional sample data.

## How to access the prototype

The whole prototype is one static file, `index.html`. It needs no server, no Python and no Docker.

### Option 1: Open it in your browser (fastest)

1. Clone or download this repo.
   - **Clone:** `git clone -b develop https://github.com/sakshijain325/NewBizEngr407.git`
   - **Download:** on GitHub, switch to the `develop` branch, then click **Code → Download ZIP** and unzip it.
2. Double-click `index.html`. It opens in your default browser.

### Option 2: Run it from VS Code with live reload (for editing)

1. Open the repo folder in VS Code (**File → Open Folder…**).
2. Install the **Live Server** extension (by Ritwick Dey).
3. Right-click `index.html` and choose **Open with Live Server**.
4. The site opens at a local address like `http://127.0.0.1:5500`. It refreshes every time you save.

### Option 3: Host it on GitHub Pages (a shareable link for the pitch)

1. In this repo, go to **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**, pick `develop` (or `main` after merging), with folder `/ (root)`, and save.
3. After a minute or two, the site is live at `https://sakshijain325.github.io/NewBizEngr407/`.

## Tour of the prototype

| Page | How to get there | What it shows |
| --- | --- | --- |
| Home | Opens by default | Value proposition, a live sample match, how it works, breeder verification, draft pricing |
| Match quiz | **Find a pet** | Nine questions on home, schedule, activity, experience, household, allergies, budget and size |
| My matches | **My matches**, or finish the quiz | Ranked animals with fit scores, reasons, concerns, and filters for species and provider type |
| Animal profile | Click any animal card | Care meters, monthly cost estimate, behavior notes, the provider's verification checklist |
| Shelter dashboard | **For shelters & breeders** | Example rescue's inquiries ranked by fit and profile completeness |

Before anyone takes the quiz, **My matches** shows the example persona "Alex," a first-time owner in an apartment. Quiz answers are saved only in your own browser.

## Where to edit

Everything is in `index.html`:

- `ANIMALS` and `PROVIDERS`: sample animal listings and shelters/breeders
- `QUESTIONS`: quiz questions and answer options
- `score()`: the matching logic (fit score, "why it fits," "ask before you meet")
- `INQ`: sample inquiries on the shelter dashboard
- `:root` at the top of the `<style>` block: colors and fonts

## Branches

- `develop`: active work on the prototype
- `main`: stable version for demos (merge `develop` into it when ready)
