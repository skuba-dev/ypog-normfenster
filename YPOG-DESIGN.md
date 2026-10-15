# YPOG Design System

Quelle: https://www.ypog.law/ (CSS `template_app.min.css`, `module_stage-text.min.css`, Logo-SVGs, Screenshots). Stand: 13. Oktober 2026. Das Design System liegt zusätzlich als Artifact vor (privat).

## 1. Brand Book

YPOG is a German law firm brand: confident, modern and warm. Pages are mostly white with black type and one decisive red; black "stage" panels carry announcements; a soft red-and-blue gradient marks page titles. Everything is built from pills, hairline rules and heavy lettering.

### Content fundamentals

- Write German first (`De / En` switch on the site). Address clients as "Mandant:innen" with the colon form; speak as "wir" ("Wir feiern die Vielfalt kluger Köpfe.", "Wir bei YPOG haben das Glück, jeden Tag mit echten Gamechangern zusammenzuarbeiten.").
- Headlines are statements, not slogans, and name the subject: "YPOG berät Personio bei Erwerb der Ausgabenmanagementplattform Circula". Use a "Pressemitteilung | 6. Oktober 2026" style date line above stage headlines; write dates out ("22. September 2026").
- Button labels are short, verb-led and sentence case: "Zur Pressemitteilung", "Alle Standorte". Filter and tag names stay as the site's own: "IP/IT/Data Protection", "Fintech + DLT", "Corporate Crime + Compliance + Investigations".
- Light/bold contrast carries emphasis: set a phrase in `h2` (weight 100) and the key words in bold ("Wir feiern die Vielfalt **kluger Köpfe.**"). No emoji, no exclamation marks.

### Visual foundations

- **Colour.** Surfaces are `surface` (white; black in the dark theme). Text is `ink`. `brand` red is for the logo, primary buttons, tags and the red stage; `accent` blue draws rules, field underlines, the focus ring and selected states. Use `brand-text` and `accent-text` for coloured text so it passes on both themes. Never put white text on `accent-bright` (3.6:1) or red text on black (`brand` is 4.0:1 there; use `brand-tint`).
- **Themes.** `light` is the site. `dark` is the black stage: use it for stage panels, the newsletter strip and anything on `black`. Inside a dark area use the `white` button, never the black one.
- **Type.** One family, MuseoSans, across five weights. Headings are weight 900 (`h1`, `h3`, `h4`, `h5`) except `h2` and `hero`, which are weight 100 with weight 300 for bold. Body copy is weight 300 in `body`; UI is `button` (600) and `nav` (300, current 800). Sizes step up at 480, 576, 768 and 1110px; the type styles list the desktop size and the notes list the steps.
- **Fonts.** MuseoSans is a licensed commercial font; its files are not part of this system. Previews fall back to Nunito Sans (from Google Fonts), then Helvetica/Arial. Add the licensed woff2 files under `fonts/` and list them in `tokens.json` to get exact rendering.
- **Spacing and layout.** Page container is `container` (1200px) with `gutter-sm` / `gutter-lg` side padding. Post lists run two columns from 768px. Stage text padding is 32 / 40 / 80px.
- **Shape.** Buttons and filter pills are always `radius-pill`; cards use `radius-card` (40px); tags, fields, rules and stages are square. Portraits are round.
- **Rules and borders.** 2px hairlines are the signature: a black rule above each nav column and footer block, a blue rule above each post. No shadows anywhere.
- **Motion.** Hovers ease over 0.4s (buttons), 0.2s (nav underline), 0.5s (posts rise 3px). Nothing bounces.
- **Imagery.** Stage artwork is the bear mark at low strength on black with a tiled grid of Y letterforms; page title bands use a blurred red/blue gradient. People appear as round portraits.
- **Focus and states.** Focus: 3px `focus` outline with 4px offset on every interactive element. Disabled: `disabled-fill` with `ink-disabled` text. Errors: `danger` text and bottom border.

### Iconography

The site uses its own icon font (`iconfont`) for arrows, search, burger and accordion chevrons; the glyph file is not included here. The nav "Expertise" entry carries a small red arrow pointing down-right. Draw replacements as simple 2px line glyphs in `ink` or `brand`; never use emoji.

### Logos

Use `ypog-logo.svg` (bear mark plus wordmark, red) in the header on white; `ypog-mark-dark.svg` for the footer; `ypog-mark-red.svg` as stage motif. See the Logos group notes. Do not redraw the mark.


## 2. Farben

Themes: `light` (Site) und `dark` (Black Stage). Fehlt ein Dark-Wert, gilt der Light-Wert.

| Token | Light | Dark | Verwendung |
|---|---|---|---|
| `brand` | `#d22332` | `#d22332` | YPOG red. Fill of primary buttons, tags, stage panels and the logo. White text on it passes (5.2:1). As text or thin line on white it passes (5.2:1); on black it is 4.0:1, so use brand-text there. |
| `brand-shade` | `#9b1928` | `#9b1928` | Hover and focus fill of primary buttons and tags; also the fifth stop of the gradient banner. White text on it passes (8.2:1). |
| `brand-tint` | `#e87780` | `#e87780` | Light red. Red text and accents on black surfaces (7.4:1 on black). Site name: primary-tint. |
| `brand-deep` | `#42070a` | `#42070a` | Deep burgundy. Only as a gradient stop in the banner and stage artwork; never as text. |
| `accent` | `#4062e3` | `#4062e3` | YPOG blue. Hairline rules above list items, borders of secondary buttons and fields, focus ring, active state fill. White text on it passes (5.2:1). |
| `accent-bright` | `#5a7dff` | `#5a7dff` | Bright blue. Blue stage panel, gradient stop, search-result rules. On black it passes 5.8:1 as text; on white only 3.6:1, so use it there for lines and fills, not text. |
| `accent-shade` | `#1b3dbb` | `#1b3dbb` | Hover fill of the active (blue) button state. White text on it passes (8.6:1). |
| `accent-tint` | `#edf1ff` | `#edf1ff` | Pale blue. Input fields, highlighted text blocks, card background. Text in ink or black on it passes (16:1). |
| `accent-tint-strong` | `#c8d2ff` | `#c8d2ff` | Stronger pale blue. Counter badges and secondary tinted fills. Text in black on it passes. |
| `black` | `#000000` | `#000000` | Absolute black. Default button fill, black stage panel, footer rules. Constant in both themes. |
| `white` | `#ffffff` | `#ffffff` | Absolute white. Text on brand, black and accent fills; white button variant. Constant in both themes. |
| `surface` | `#ffffff` | `#000000` | Page background. Light: white. Dark: the black stage and hero panels. |
| `surface-field` | `#edf1ff` | `#ffffff1a` | Background of text inputs and textareas. Light: accent-tint. Dark: white at 10%, as in the newsletter field. Text in ink on it passes in both themes. |
| `ink` | `#121212` | `#ffffff` | Body copy, headings, nav links and icons on surface and surface-field. 18.7:1 on white; white on black in the dark theme. |
| `ink-muted` | `#595959` | `#bfbfbf` | Secondary text: job titles, legal notes, small captions on surface. 7.0:1 on white; 11:1 on black. |
| `ink-disabled` | `#989898` | `#989898` | Text of disabled buttons on disabled-fill. Below 4.5:1 by the site's own choice (2.4:1); disabled controls are exempt, but never use it for readable copy. |
| `disabled-fill` | `#eeeeee` | `#333333` | Fill and border of disabled buttons. |
| `brand-text` | `#d22332` | `#e87780` | Red text and links on surface: the nav underline, hover icons, red emphasis. 5.2:1 on white (light) and 7.4:1 on black (dark). |
| `accent-text` | `#4062e3` | `#5a7dff` | Blue text on surface: active accordion title, card headline, links. 5.2:1 on white; 5.8:1 on black. |
| `rule` | `#121212` | `#ffffff` | Heavy 2px rules: nav column tops, footer dividers. 3:1 or better on surface in both themes. |
| `rule-accent` | `#4062e3` | `#5a7dff` | 2px rule above list items and teasers on surface. Both pass 3:1 on their surface (5.2:1 and 5.8:1). |
| `rule-subtle` | `#d9d9d9` | `#333333` | Quiet hover border and dividers inside components. Decorative only; carries no meaning alone. |
| `focus` | `#4062e3` | `#5a7dff` | Focus ring colour: 3px solid, 4px offset. 5.2:1 on white, 5.8:1 on black. |
| `on-tint` | `#121212` | `#121212` | Text on any -tint fill (accent-tint, success-tint, danger-tint, warning-tint). Constant in both themes. |
| `danger` | `#dc3545` | `#dc3545` | Error text and error borders on form fields (4.5:1 on white, 4.6:1 on black); fill with white text 4.5:1. |
| `danger-tint` | `#f8d7da` | `#f8d7da` | Background of error messages and alerts. Text in on-tint. |
| `success` | `#246132` | `#246132` | Success fill with white text (7.4:1). Defined in the site's utility classes. |
| `success-tint` | `#d4edda` | `#d4edda` | Background of success messages. Text in on-tint. |
| `warning` | `#ffc107` | `#ffc107` | Warning fill. Text on it must be black (not white). Defined in the site's utility classes. |
| `warning-tint` | `#fff3cd` | `#fff3cd` | Background of warning messages. Text in on-tint. |
| `info` | `#17a2b8` | `#17a2b8` | Info fill. Defined in the site's utility classes; use black text on it (6.9:1), not white. |
| `info-shade` | `#098ba0` | `#098ba0` | Darker teal info fill (site name: info-shade). White text on it is 4.0:1 and misses 4.5:1: use it only for 19px bold text or larger, or use black text on info instead. |
| `pride-orange` | `#ffa564` | `#ffa564` | Diversity button border gradient only (with brand, yellow, green, blue, violet). |
| `pride-yellow` | `#fbff29` | `#fbff29` | Diversity button border gradient only. |
| `pride-green` | `#2cb016` | `#2cb016` | Diversity button border gradient only. |
| `pride-blue` | `#0500ff` | `#0500ff` | Diversity button border gradient only. |
| `pride-violet` | `#ad4ef9` | `#ad4ef9` | Diversity button border gradient only. |

### Kontrastprüfung (WCAG 2)

| Paar | Verhältnis |
|---|---|
| Weiß auf `brand` | 5,2:1 |
| Weiß auf `brand-shade` | 8,2:1 |
| `brand-text` auf Weiß / auf Schwarz (Dark) | 5,2:1 / 7,4:1 |
| `accent-text` auf Weiß / auf Schwarz (Dark) | 5,2:1 / 5,8:1 |
| `ink` auf Weiß / Weiß auf Schwarz | 18,7:1 / 21:1 |
| `ink-muted` auf Weiß / auf Schwarz | 7,0:1 / 11,4:1 |
| Weiß auf `accent` / `accent-shade` | 5,2:1 / 8,6:1 |
| `ink` auf `accent-tint` | 16,6:1 |
| `brand` auf Schwarz (Fehlpaar, nur ≥24px/Grafik) | 4,0:1 |
| Weiß auf `accent-bright` (Fehlpaar, nicht für Text) | 3,6:1 |
| Weiß auf `info-shade` (Fehlpaar, nur ≥19px fett) | 4,0:1 |
| `ink-disabled` auf `disabled-fill` (Site-Wert, Disabled ausgenommen) | 2,4:1 |

## 3. Typografie

Familie: `"MuseoSans", "Nunito Sans", Helvetica, Arial, sans-serif` (MuseoSans, Gewichte 100/300/500/700/900 inkl. Kursiv; Nunito Sans nur als Vorschau-Ersatz).

### Display

| Stil | Größe | Zeilenhöhe | Gewicht | Spacing | Verwendung |
|---|---|---|---|---|---|
| `hero` | 90px | 1.04 | 100 | 0 | Oversized statement line, light weight, on surface. 36px on phones, 60px from 576px, 90px from 1110px. Bold the key words with weight 300. |
| `stage-headline` | 40px | 1.2 | 900 | 0 | Headline in a stage panel beside the image, white on black. 32px up to 1440px, 40px from 1440px, 48px from 1920px. |
| `stage-pre-headline` | 24px | 1.3 | 300 | 0 | Date line above a stage headline, e.g. Pressemitteilung / 6. Oktober 2026. |

### Headings

| Stil | Größe | Zeilenhöhe | Gewicht | Spacing | Verwendung |
|---|---|---|---|---|---|
| `h1` | 54px | 1.19 | 900 | 0.5px | Page title. 30px on phones, 38px from 576px, 46px from 768px, 54px from 1110px. |
| `h2` | 46px | 1 | 100 | -0.29px | Section title in light weight; key words in weight 300 via strong. 28px on phones, 40px from 768px, 46px from 1110px. |
| `h3` | 36px | 1.28 | 900 | -0.47px | Teaser and list headline. 24px on phones, 32px from 768px, 36px from 1110px. |
| `h4` | 28px | 1.21 | 900 | 0.5px | Sub-section title. 22px on phones, 26px from 768px, 28px from 1110px. |
| `h5` | 22px | 1.36 | 900 | -0.5px | Small title. 20px on phones, 22px from 576px. |

### Text

| Stil | Größe | Zeilenhöhe | Gewicht | Spacing | Verwendung |
|---|---|---|---|---|---|
| `intro` | 22px | 1.64 | 300 | 0 | Lead paragraph below a page title. 20px on phones, 22px from 576px. |
| `special` | 24px | 1.21 | 300 | 0 | Pull quote or call-out line. 20px on phones, 22px from 576px, 24px from 1110px. |
| `body` | 18px | 1.56 | 300 | 0 | Running text in weight 300. 16px on phones, 17px from 480px, 18px from 576px. Colour ink on surface. |
| `body-strong` | 18px | 1.56 | 900 | 0 | Emphasis inside body text, e.g. a defined term. |
| `list-title` | 20px | 1.21 | 300 | 0.43px | Title of a post in a list. 18px on phones, 20px from 576px, 24px from 1110px. In the featured (hero) post: weight 900, 26px, letter-spacing -0.47px. |
| `caption` | 14px | 1.2 | 300 | 0 | Date under a post and legal notes. Colour ink-muted for legal notes. |

### UI

| Stil | Größe | Zeilenhöhe | Gewicht | Spacing | Verwendung |
|---|---|---|---|---|---|
| `button` | 18px | 1 | 600 | 0 | Label of pill buttons and filter pills. 16px on phones, 17px from 480px, 18px from 576px. Browsers render weight 600 as 700 with the MuseoSans files. |
| `nav` | 16px | 1 | 300 | 0 | Main navigation links. Current page and current language: weight 800. |
| `tag` | 14px | 1 | 900 | 0.25px | Label inside a tag chip. |


## 4. Spacing & Layout

| Token | Wert | Verwendung |
|---|---|---|
| `space-1` | `5px` | Gap between buttons in a button group; padding of a tag chip (5px 7px). |
| `space-2` | `8px` | Right margin between tag chips; half step in compact lists. |
| `space-3` | `16px` | Standard gap and nav list item padding (1rem); field padding in the newsletter field. |
| `space-4` | `24px` | Top padding of a list item below its blue rule. |
| `space-5` | `32px` | Horizontal padding of buttons (32px); stage text padding on phones. |
| `space-6` | `40px` | Card and stage padding from 992px; vertical gap between list items. |
| `space-7` | `80px` | Stage text padding from 1200px. |
| `space-8` | `96px` | Top padding of the footer on desktop (6rem). |
| `gutter-sm` | `15px` | Side padding of the page container on phones. |
| `gutter-lg` | `45px` | Side padding of the page container from 576px. |
| `container` | `1200px` | Max width of the page container (g-container), including the gutters. |

## 5. Radius

| Token | Wert | Verwendung |
|---|---|---|
| `radius-pill` | `100px` | Buttons, filter pills and the newsletter submit button: always fully rounded. |
| `radius-card` | `40px` | Large cards on accent-tint (c-card). |
| `radius-field` | `5px` | Checkbox boxes in forms. |
| `radius-round` | `50%` | Round portraits (staff and contact images), carousel bullets and the round search button. |

## 6. Rahmen

| Token | Wert | Verwendung |
|---|---|---|
| `border-rule` | `2px` | Rule above navigation columns, list items, footer blocks; border of buttons and filter pills. |
| `border-focus` | `3px` | Width of the focus outline (offset 4px). |
| `border-diversity` | `4px` | Border of the Diversity button. |

## 7. Breakpoints (min-width)

| Token | Wert | Verwendung |
|---|---|---|
| `bp-xs` | `480px` | Phone landscape: type steps up one. |
| `bp-sm` | `576px` | Container gutters widen to 45px; type steps up. |
| `bp-md` | `768px` | Tablet: headings step up. |
| `bp-lg` | `992px` | Desktop navigation and stage layout switch from stacked to side by side. |
| `bp-xl` | `1110px` | Largest heading sizes (h1 54px, hero 90px). |

## 8. Logos

Logos of YPOG, copied unchanged from ypog.law (header and footer SVGs).

- `ypog-logo.svg`: bear mark plus the YPOG wordmark, all in brand red `#d22332`. The header logo; use it on `surface` in the light theme and on white or very light grounds only.
- `ypog-mark-red.svg`: the bear mark alone in `#d22332`. Recoloured copy of the footer mark; use it as a favicon-size mark, a stage motif on black, or as a watermark.
- `ypog-mark-dark.svg`: the bear mark alone in `#121212` (the footer logo). Use on white or `accent-tint`.

All three are single-ink SVGs with the colour baked in; `<img>` cannot recolour them, so pick the file whose ink reads on the ground. Keep clear space of one mark-width on all sides and never stretch, outline or recolour the wordmark. The site header shows the logo at 100px wide on phones, 190px on tablets and 250px on desktop; it shrinks to 100/150px when the page is scrolled.

Dateien: `ypog-logo.svg`, `ypog-mark-red.svg`, `ypog-mark-dark.svg` (Originale von ypog.law; im Artifact unter Logos).


## 9. Komponenten

React-Bundle `window.YPOG` (`Button`, `Tag`, `Nav`, `TextField`, `PostTeaser`, `HeadlineBanner`, `Stage`); Styles in `bundle.css`, Typen in `index.d.ts`.

### Button

Pill-shaped button and link-button for every action on the site: default black, red primary, blue-outlined secondary, outline/active filter pills and a white version for dark stages.

Provide a short label as `children` (sentence case, German, no icons needed); pass `href` for navigation (renders `<a>`), otherwise `onClick` (renders `<button>`).

- Use `primary` (brand red) once per view for the main action; use the default black for the usual call to action (e.g. "Zur Pressemitteilung").
- Use `secondary` for a quiet second action next to a primary; use `white` on black or red stages; never put the default black button on a black surface.
- Use `outline` for filter pills (Berlin, Hamburg, …) and switch the selected one to `active`; use `blue` only when the site marks a selection in blue.
- `diversity` is reserved for the Diversity + Inclusion call to action: it is the one place the rainbow border appears.
- Padding is 18px 32px 16px, border 2px, radius `radius-pill`. Hover inverts: black becomes white with black text; primary darkens to `brand-shade`.
- The focus ring is `focus`, 3px, offset 4px, and must stay visible. Disabled buttons use `disabled-fill` and `ink-disabled` and give no hover.

### Tag

Small red category chip that labels a post (IP/IT/Data Protection, Financial Services, Briefing).

Provide the category name as `children`; add `href` to link it to the filtered list. Place tags in a row below the post title, before the date; the 8px right margin spaces them.

- Colour is always `brand` with white text; hover darkens to `brand-shade`. Do not recolour tags per category.
- Tags are square (no radius) and set in weight 900 at 14px; the pill shape belongs to buttons only.
- Keep names exactly as the site's categories; do not shorten them.

### Nav

Main navigation: link columns, each under a 2px black rule, with a red underline that grows on hover.

Provide `columns`, an array of columns, each an array of `{label, href, active}`. The live site uses four columns: Home/Expertise/Events, Insights/Presse, Team/Karriere/Kontakt and the language switch De / En; the current item is `active` (weight 800).

- Links are `ink` on `surface`, 16px, weight 300; never colour a nav link red at rest.
- Hover shows a 2px `brand` underline sliding from left to right; focus shows the 3px `focus` outline.
- Keep each column at most 160px wide and put the logo at its left; on phones the columns collapse into a full-screen menu from the burger button (not included here).

### TextField

Form field with a pale blue ground and a 2px blue rule underneath, for single-line inputs and textareas.

Provide `label`, and `value`/`onChange` or `defaultValue`; set `multiline` for a textarea (min height 150px on the site), `error` for the message text and `hint` for help text.

- The field fills with `surface-field` and the bottom border is `accent` (`danger` in the error state); there is no outline border and no radius.
- Text is `ink` at weight 400, placeholder text is `ink` too, so it stays readable; label above in weight 500.
- Show errors in `danger` below the field in plain German sentences; mark `aria-invalid`.
- On black surfaces the field turns into a 10% white fill with white text, as in the newsletter box.

### PostTeaser

Post item for the Insights list: a 2px blue rule on top, then the title, tag chips, the date and an excerpt.

Provide `title`, `href`, optional `tags` (strings), `date` (written out: "22. September 2026") and `excerpt`. Use `featured` for the lead post at the top of a list.

- Titles are weight 300 at 24px with +0.43px tracking; the featured title is weight 900 at 26px with -0.47px tracking.
- The rule above is `rule-accent`, 2px; the item lifts 3px on hover.
- Keep the title as a link in `ink`, never underlined or blue.
- Place two items per row from 768px, one on phones.

### HeadlineBanner

Full-width page title band: a red field with a soft blue-and-burgundy gradient and the page name in white, as on Insights and Team.

Provide `title` (one or two words) and optional `subtitle`. Place it directly under the header.

- Title is `h1` style in white (54px on desktop, weight 900). White on `brand` passes 5.2:1; do not move the title onto the blue part of the gradient.
- The site animates the gradient with a script from `brand`, `brand-deep`, `brand`, `accent-bright` and `brand-shade`. This component paints a static approximation; the animation is not part of the system.
- The container inside is 1200px wide with the usual gutters.

### Stage

Home-page stage: a coloured panel with the date line and headline bottom-left, the call-to-action button, and artwork to the right.

Provide `headline`, optional `preHeadline` (type of announcement and date), `cta` and `ctaHref`, `tone` (black, white, red or blue) and `media` for the artwork on the right (e.g. the red bear mark).

- Black is the lead tone. Text is white on black; on red it is white; on the bright blue it must be black (white on `accent-bright` is only 3.6:1).
- The call to action uses the `white` button on black and red, the default black button on white.
- Text column is 35% wide from 992px (stacked on phones); padding 32px, 40px from 992px and 80px from 1200px. Headline is 32px, 40px from 1440px, 48px from 1920px, weight 900.
- The artwork is the mark at low strength (dark red on black) with a grid of Y glyphs; supply it as an image.


### Props im Überblick

| Komponente | Props |
|---|---|
| `Button` | `variant` (default, primary, secondary, white, outline, active, blue, diversity), `href`, `disabled`, `type`, `onClick`, `children` |
| `Tag` | `href`, `children` |
| `Nav` | `columns` (Array von Spalten mit `{label, href, active}`), `label` |
| `TextField` | `label`, `id`, `type`, `multiline`, `placeholder`, `value`, `defaultValue`, `onChange`, `error`, `hint` |
| `PostTeaser` | `title`, `href`, `tags`, `date`, `excerpt`, `featured` |
| `HeadlineBanner` | `title`, `subtitle` |
| `Stage` | `tone` (black, white, red, blue), `preHeadline`, `headline`, `cta`, `ctaHref`, `media` |

### Cover

960 × 300 px: Rote Platte, blauer Block, Ink-Block mit 20 Y-Glyphen aus dem Logo (Raster 40/38 px), pale-blauer Block mit roter Pille (`radius-pill`), Burgunder-Block; links der Name „YPOG" in Gewicht 900 (120 px) mit der Zeile „Wir feiern die Vielfalt kluger Köpfe."


## 10. Lücken und offene Punkte

- **MuseoSans** ist lizenzpflichtig; die woff2-Dateien sind nicht enthalten. Vorschauen nutzen Nunito Sans als Ersatz. Für exakte Darstellung Dateien unter `fonts/` ablegen und in `tokens.json` (`type.fonts`) eintragen. Die Site lädt `34BE01_*.woff2` von ypog.law (Gewichte 100, 300, 500, 700, 900, je normal/kursiv).
- **Icon-Font** (`iconfont`) der Site ist nicht enthalten.
- **HeadlineBanner**: Der animierte Gradient der Site ist nur statisch angenähert.
- **Abgedeckte Seiten:** Startseite, Insights, Team. Nicht als Komponenten gebaut: Footer, Akkordeon, Karussell, Suche, Kontaktkarten, Burger-Menü, Newsletter-Feld, Karte (`c-card`, 40 px Radius, nur als Token).
- **Annahme:** Schriftgrößen oberhalb 576 px für `h5` und `body` sind aus den sichtbaren Breakpoints abgeleitet; nicht jeder Zwischenschritt wurde gegen das CSS geprüft.
- **Statusfarben** (`success`, `warning`, `info`) stehen in den Utility-Klassen der Site; ihre Verwendung im Frontend wurde nicht beobachtet.
- **Logo-Upload:** Die hochgeladene `YPOG-logo_header.svg` erreichte die Sitzung nicht; das Logo wurde per Browser direkt von der Site geholt.
