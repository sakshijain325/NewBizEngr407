# TailMates

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

Sign in with one of four demo accounts (no passwords). Each account only sees its own pages.

| Account | Role | What to try |
| --- | --- | --- |
| Alex Rivera | Adopter | Take the 4-part quiz, open a match, read "How we calculated this", save and compare pets, apply and track the application |
| Ridgeline Animal Rescue | Verified shelter | Open an application, request missing info, schedule a meeting, mark an animal unavailable, add a listing |
| Mapleleaf Poodles | Verified breeder | See the waitlist with Priority members ordered first |
| Sunny Acres Goldens | New breeder, not verified | Listings stay locked until every verification step is done |

Public pages (no sign-in): home, **Browse** (area inventory), **For shelters**, **For breeders**.

**Try the two-sided demo:** apply to a Ridgeline animal as Alex, switch to the Ridgeline account and request information, then switch back to Alex and answer it in **Applications**.

Demo data is saved in your own browser only. Use **Reset demo** in the footer to start over.

## How matching works

1. **Must-haves and safety checks first.** A failed must-have (for example, a cat in the home and an animal that isn't safe with cats) rules the animal out. If an animal can't be alone as long as your home is empty and you have no care plan, it's shown as "Needs a care plan" (capped at 55). An unassessed must-have is shown as "Needs info first" (capped at 74).
2. **Preferences are then scored out of 100:** daily time (20), training needs (15), monthly cost (15), personality (12), time alone (10), grooming (8), age (6), size (5), distance (5), nice-to-haves (4).
3. Every animal shows the reasons, the concerns, what's unknown, and an itemized cost estimate (monthly, care-plan extras, up-front, first year).

The score is a compatibility estimate, not a guarantee.

## Where to edit

Everything is in `index.html`:

- `ANIMALS` and `PROVIDERS`: sample animal listings, shelters/breeders and their verification records
- `QUESTIONS` and `SECS`: quiz questions, answer options and the four sections
- `evaluate()`: the matching logic (must-haves, care plans, factor weights, explanations)
- `costs()`: itemized cost estimates and platform fees
- `SEED_APPS`: sample applications on the dashboards
- `pricing()`: the pricing section
- `:root` at the top of the `<style>` block: colors and fonts

## Branches

- `develop`: active work on the prototype
- `main`: stable version for demos (merge `develop` into it when ready)
