# DA Calculator — installable app

Dearness Allowance and arrears under APGENCO Revised Pay Scales 2022,
covering G.O.O. 167 and 168 of 07.09.2026.

## Why the plain HTML file kept failing

An HTML file sent over WhatsApp lands in a temporary folder. The phone clears
that folder, some file managers open it in a viewer that cannot run scripts, and
the file has no icon, so people mistake it for a PDF and lose it.

Put these files on a web address once. Everyone opens the link, taps Install, and
after that the app sits on the home screen with its own icon and opens with no
internet at all.

## What is in this folder

| File | What it does |
|---|---|
| `index.html` | The calculator itself |
| `manifest.webmanifest` | Name, icon and colours the phone uses when installing |
| `sw.js` | Keeps everything on the phone so it opens offline |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | Home screen icons |
| `apple-touch-icon.png` | Icon for iPhone and iPad |

All five must sit in the same folder, keeping these exact names.

## Hosting it free on GitHub Pages

1. Sign in at github.com and create a new public repository named `da-calculator`.
2. On the repository page choose **Add file → Upload files**, drag in every file
   from this folder, and commit.
3. Open **Settings → Pages**. Under Source pick **Deploy from a branch**, choose
   branch `main` and folder `/ (root)`, then save.
4. Wait a minute or two. Your address appears at the top of the same page, in the
   form `https://<your-username>.github.io/da-calculator/`.
5. Share that link. Nothing else to maintain.

Netlify Drop (`app.netlify.com/drop`) and Cloudflare Pages work the same way if
you would rather drag the folder in and get a link straight away.

## Installing on a phone

An **Install app** button sits at the bottom of the page and stays there while
you scroll. Tap it. On Android Chrome the install box comes up straight away; on
any other browser the same button opens a short card with the two or three taps
that browser needs. Once installed the button reads **Installed** and greys out.

Alongside it is **Print everything**, which prints or saves a PDF of the whole
sheet, including the month-by-month table that stays folded away on screen. The
printout carries a heading with the name, designation, scale, increment month,
basic pay and the date, so it can go straight into a file.

After installing, aeroplane mode is fine — the calculator still opens and works.

## Pushing an update later

Upload the changed `index.html`, then open `sw.js` and change the first line
from `da-calc-v1` to `da-calc-v2`. Without that change phones keep serving the
old copy from their cache.

## What it calculates

Pick Workmen or Other than Workmen, the grade and the scale under the Automatic
Advancement Scheme, then set your annual increment month.

The arrears period is fixed by the two G.O.s and always breaks into three:

| Period | Dates | Rate difference | Months |
|---|---|---|---|
| 1 | 01.01.2025 – 30.06.2025 | 1.95% | 6 |
| 2 | 01.07.2025 – 31.12.2025 | 3.58% | 6 |
| 3 | 01.01.2026 – 31.08.2026 | 5.20% | 8 |

Each period has its own basic pay dropdown listing every stage of your scale with
its stage number. Where your increment month falls inside a period, that period
splits into two boxes on its own, so a July increment gives four boxes and an
April increment gives five. A January increment falls on the first day of periods
1 and 3, so it needs no split and three boxes are enough.

Choose the basic pay you draw now and every box fills itself, stepping back one
stage of the scale at each increment. Change any box if a promotion, stagnation
increment or Personal Pay makes it different, and use **Refill from the scale**
to undo your edits. Each period shows its own arrear as you go.

The app then compares the DA due at each revised rate against the 14.07% already
drawn, month by month.

Three figures head the result: the DA payable from September 2026 and how much
more that is every month, the total arrears with the size of each instalment,
and the two added together, which is what actually lands in the September 2026
pay bill.

Below that, the three DA sanctions are set out one by one. Each row shows the
rate it added, the cumulative rate it took you to, what it adds to your monthly
DA, and the share of the arrears it carries. A sanction from January 2025 has
been owed for all twenty months; one from January 2026 for only eight. The three
shares add up to the total arrears.

Figures are indicative. The pay bill drawn by the Pay Officer or Drawing Officer
is final.

Prepared by Lingam Sravan Kumar, Junior Assistant, Dr. NTTPS.
