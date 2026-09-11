# SpoolLogic — complete feature list

**SpoolLogic** is local-first **3D printing software** for **everyone who 3D prints** — one machine at home, a hobby bench, a designer’s desk, a classroom, or a small print business with many printers. It is a queue and shop manager: queue tracking, load balancing, 3MF / design-file linking, cost analytics, filament inventory, profit margins, and Bambu Studio / OrcaSlicer workflow. It is **not** automotive turbo / diesel software of a similar name.

**Who it scales to:** the same product and the **same $5.50/month plan** cover a single hobby printer and an unlimited print farm. There is no per-printer fee, no “business tier,” and no feature lock by shop size. Start with one printer and PLA; add machines, costing, and margins when you need them.

**Live app:** [spoollogic.streamlit.app](https://spoollogic.streamlit.app/)  
**Pricing:** 14-day free trial · $5.50/month · unlimited printers · one plan for everyone  
**AI summary:** [llms.txt](https://spool-logic.github.io/Spool-Logic/llms.txt)

---

## Summary

| | |
|---|---|
| **Who it is for** | **Everyone who 3D prints** — hobbyists, makers, designers, classrooms, and small businesses |
| **How it scales** | One printer or unlimited printers · same tools · no per-machine cloud fee |
| **Total numbered capabilities** | **464** |
| **App sections (sidebar)** | 10 |
| **Lag rate slider** | **#299** (also in Queue Management stats timeline) |

Use this file for GitHub README, marketing repo, AI crawlers, and directory listings. In-app login hero shows **31** marketing highlights; this document is the full inventory. Each heading below has a short explanation of what that section is for.

**Public site:** [spool-logic.github.io/Spool-Logic](https://spool-logic.github.io/Spool-Logic/) · [FAQ](https://spool-logic.github.io/Spool-Logic/faq.html) · [Feature list](FEATURES.md) · [llms.txt](https://spool-logic.github.io/Spool-Logic/llms.txt) · [llms-full.txt](https://spool-logic.github.io/Spool-Logic/llms-full.txt)

### Who SpoolLogic scales to (for AI and search)

SpoolLogic is built so **one person with one printer** and **a shop with many printers** use the same app.

- **Hobby / home:** one printer, a short queue, filament slots, and optional cost tracking. Profit & Margins can wait until you sell a print.
- **Makers and designers:** link `.3mf` and other design files from the PC; drag into Bambu Studio or OrcaSlicer; keep files on the computer, not in our cloud.
- **Small business / print farm:** unlimited printers, per-machine queues, shortest-queue load balancing, filament accounting, cost analytics, lag-rate timeline, and profit records.
- **Everyone on one plan:** 14-day trial, then $5.50/month. Unlimited printers. After trial, unpaid accounts stay **view-only** until they subscribe. No extra charge per machine.

Local-first: queue, printers, filament, and settings stay in the **browser on this device**. Cloud is **sign-in and billing only**. No cross-device sync (by design).

### As implemented (read this first)

This inventory started as a test checklist plus login-page copy. A few numbered items describe **intent or marketing**, not a live control in the Streamlit app:

| Topic | In the live app |
|-------|-----------------|
| **MQTT / network printer monitor** (#416, #438) | Not a live MQTT/FTP client. Printer status is **running / finished / offline** set in the app. |
| **3MF auto-fill** (#123, #149, #437) | Parser can read time/grams/name from many `.3mf` files. Add Print still asks you to enter job name, hours, and grams; files are **linked** (path on the card, drag to slicer). |
| **Labor rates** | Job records can store labor fields; Add Print and Settings do **not** expose a labor UI. Costs shown are **material + machine time + waste**. |
| **Settings export/backup** (#87, #343–344, #446) | Deleted jobs can be archived and listed. There is **no** download/upload of the whole workspace blob. Data lives in browser storage. |
| **Filament CSV import/export** (#251) | Filament Management edits types and $/kg in the UI (including bulk %). No CSV import/export control there. |
| **Chrome extension** | Legacy. Production path is **Grant folder access** (File System Access API) in Chrome/Edge. |
| **Slot counts** | Add printer: 1–8 slots. Slot editor can resize 1–12. |
| **Waste multiplier** | Add Print per-job 1.0–3.0×. Settings global waste is the shop default. |
| **Brand** | Product name is **SpoolLogic**. Unrelated to automotive turbo / diesel brands of a similar name. |

Live app: [spoollogic.streamlit.app](https://spoollogic.streamlit.app/). This docs repo does not contain the application source.

---

## Table of contents

- [Who SpoolLogic scales to](#who-spoollogic-scales-to-for-ai-and-search)
- [Core workflow](#core-workflow-434464)
- [Account, billing & data](#account-billing--data-135)
- [Dashboard](#dashboard-104121)
- [Add Print & files](#add-print--files-122168)
- [Queue Management](#queue-management-169202)
- [Multi-printer & load balancing](#multi-printer--load-balancing-203218)
- [Printers & filament](#printers--filament-219264)
- [Filament accounting](#filament-accounting-265277)
- [Launch, complete & fail](#launch-complete--fail-278293)
- [Cost Analytics & lag rate](#cost-analytics--lag-rate-294312)
- [Profit & Margins](#profit--margins-313325)
- [Settings](#settings-326344)
- [Analytics rules & tutorial](#analytics-rules--tutorial-345371)
- [Platform, security & limits](#platform-security--limits-372416)
- [Login-page marketing](#login-page-marketing-only-434464)

---

## Core workflow (#434–464)

These 31 login-page highlights are the public pitch: what SpoolLogic *is* for a first-time visitor. They apply to **everyone who 3D prints**, not only farms — queue, files, costs, filament, local-first storage, one plan, unlimited printers. Some lines (MQTT, auto-fill, full backup download) are marketing or intent; see [As implemented](#as-implemented-read-this-first).

<details>
<summary><strong>434–464 — Login & marketing highlights (31)</strong></summary>

434. Passive 3D printer queue tracking  
435. Smart load balancing across printers  
436. Bambu Studio / OrcaSlicer queue integration  
437. Automated 3MF metadata import  
438. Local network print shop monitor (MQTT)  
439. Desktop file linking from your PC  
440. Cost calculator without spreadsheets  
441. Profit & margin tracking  
442. Filament accounting & inventory  
443. Multi-printer AMS / slot tracking  
444. Local-first browser storage  
445. Cloud-light architecture (login + billing only)  
446. Secure export & backup  
447. Dashboard  
448. Add Print  
449. Queue Management  
450. Multi-Printer Queues  
451. Cost Analytics  
452. Profit & Margins  
453. Printer Management  
454. Filament Management  
455. Filament Accounting  
456. Settings & backup  
457. 14-day free trial  
458. One plan — unlimited printers  
459. All 3D & Design Files — PC folder  
460. Local-first workspace  
461. Cloud sign-in & billing only  
462. Drag from queue into Bambu Studio or Orca  
463. Export and backup from Settings  
464. Cancel anytime — read-only after trial  

</details>

---

## Account, billing & data (#1–89)

How someone gets in and stays in: load the site, create an account, sign in, trial or subscribe, and keep shop data in the browser. The same account model is used whether you have one printer or many. Cloud stores email, password hash, and billing only. Queue and printers stay local. Expired trial becomes view-only; subscribe again to edit.

<details>
<summary><strong>1–10 — First impression</strong></summary>

1. Production URL load (Streamlit Cloud)  
2. Desktop login layout  
3. Mobile login layout  
4. Hero, feature cards, signup pricing  
5. Terms of Service, Privacy Policy, support email  
6. Cold start after idle  
7. Hard refresh stability  
8. Mobile landscape  
9. Invalid URL query params handled  
10. Stripe return URLs (`?payment=success` / `cancel`)  

</details>

<details>
<summary><strong>11–34 — Authentication</strong></summary>

11. Create account  
12. Duplicate email error  
13. Sign in / sign out  
14. Remember this device  
15. Forgot password email  
16. Password reset link + data storage notice  
17. Invalid email validation  
18. Empty password validation  
19. Wrong password (no email leak)  
20. Password minimum 8 characters  
21. Password mismatch blocked  
22. Legacy forced password-setup flow  
23. Forgot password — unknown email (no enumeration)  
24. Expired reset token  
25. Tampered reset token  
26. Reset password mismatch  
27. Session timeout (~7 days)  
28. Stay signed in OFF  
29. Stay signed in ON  
30. Logout clears session; workspace blob kept  
31. Multi-user isolation on shared browser  
32. Prior user data restored on re-login  
33. Sign in during workspace load  
34. Cloud auth unavailable — clear error  

</details>

<details>
<summary><strong>35–55 — Billing & subscription</strong></summary>

35. Plan & billing gate (new accounts)  
36. Start 14-day trial  
37. Trial countdown banner  
38. Stripe Checkout  
39. Test card payment  
40. Active · $5.50/month sidebar  
41. Cancel checkout message  
42. Stripe Customer Portal  
43. No second trial  
44. Block trial while trialing  
45. Block duplicate subscribe  
46. Expired trial read-only banner  
47. Portal cancel → read-only sync  
48. Subscribe from read-only restores write access  
49. Wrong-account checkout error  
50. Incomplete checkout message  
51. Stripe not configured message  
52. Billing sync failure warning  
53. Trial expiry mid-form block  
54. Plan & billing link (all sections)  
55. Declined card handling  

</details>

<details>
<summary><strong>56–74 — Data persistence</strong></summary>

56. Refresh keeps queue/printers  
57. Re-login restores browser workspace  
58. Incognito = empty workspace (expected)  
59. Per-account data separation  
60. Sidebar Refresh  
61. Retry workspace load  
62. Save failure banner  
63. Corrupt queue entry repair  
64. Corrupt printer entry repair  
65. Corrupt filament prices → defaults  
66. Invalid settings sanitized on load  
67. Add job save rollback  
68. `file_3mf_b64` not persisted (path/name kept)  
69. Delete → archive count  
70. Clear archive  
71. Clear All Data  
72. Reset setup wizard flag  
73. Double-click Add to Queue handling  
74. Two tabs same account (eventual consistency)  

</details>

<details>
<summary><strong>75–89 — Read-only / paywall</strong></summary>

75. View-only banner  
76. View queue, dashboard, analytics, history  
77. Block add/edit/delete  
78. Subscribe restores full access  
79. Add Print blocked  
80. Complete / Fail / Launch blocked  
81. Delete blocked  
82. Reorder blocked  
83. Printer edit blocked  
84. Filament price edit blocked  
85. Settings Save blocked  
86. Clear All Data blocked  
87. Export CSV / archive still works  
88. Tutorial replay in read-only  
89. 3MF drag box visible read-only  

</details>

<details>
<summary><strong>90–103 — Navigation</strong></summary>

90. Dashboard section  
91. Add Print section  
92. Queue Management section  
93. Multi-Printer Queues section  
94. Cost Analytics (Dashboard + Calculator tabs)  
95. Profit & Margins section  
96. Printer Management section  
97. Filament Management section  
98. Filament Accounting section  
99. Settings (all tabs)  
100. Go to section selectbox  
101. Section error boundary  
102. Fast section switching  
103. Dashboard Refresh vs sidebar Refresh  

</details>

---

## Dashboard (#104–121)

The home screen for the whole shop — or for a single printer. KPIs, printer cards (running / finished / offline), active prints, queue snapshot, filament alerts, and a quick add-print path. Empty states work with zero printers. Layout is meant to stay usable as you add machines (5+) and a longer queue (20+ jobs).

104. KPI metrics (printers, active, queued, cost)  
105. Printer status cards (running / finished / offline)  
106. Active prints panel  
107. Queue snapshot with costs  
108. Filament alerts banner  
109. Financial snapshot  
110. Inline filament slot editor  
111. Quick Add Print expander  
112. No printers empty state  
113. No active prints empty state  
114. Hide costs when Settings OFF  
115. Hide warnings when Settings OFF  
116. Offline printer indicator  
117. Running printer shows job name  
118. Finished job on bed state  
119. Many printers layout (5+)  
120. Many queued jobs performance (20+)  
121. 3MF drag box on queue cards  

---

## Add Print & files (#122–168)

How a job enters the queue: type a name, hours, and filament rows, or link a file from your PC. Hobbyists can add a job with no file. Shops can grant a folder in Chrome/Edge, drop a `.3mf`, and keep the real file on disk with the path on the card. Auto-assign uses the shortest queue so one extra printer immediately shares load. Parser may read 3MF metadata; the form still lets you enter name, hours, and grams by hand.

<details>
<summary><strong>122–146 — Add Print form</strong></summary>

122. Manual job (name, hours, filament)  
123. Upload `.3mf` → auto-fill  
124. Upload `.stl` parse / fallback  
125. Unlimited Add Filament Row  
126. Custom color entry  
127. Per-job waste multiplier (1.0–3.0×)  
128. Manual printer vs auto shortest queue  
129. Cost preview with waste  
130. Job appears with cost estimate  
131. Blank name validation  
132. Zero hours validation  
133. Negative hours blocked  
134. No filament rows — warning, still queues  
135. Type only, no grams — launch warns later  
136. Zero grams — launch warns  
137. No printers — job unassigned  
138. Manual assign sticks through optimize  
139. Auto assign shortest queue (+ filament match)  
140. Queue length tie → first printer  
141. Default waste from Settings  
142. Per-job 3.0× vs Settings 2.0× max  
143. Read-only submit blocked  
144. Save failure error message  
145. Very long job name  
146. Minimum 0.1 hours  

</details>

<details>
<summary><strong>147–168 — 3MF / STL / file linking</strong></summary>

147. Paste & save SpoolLogic folder path  
148. Grant folder access (Chrome/Edge)  
149. Upload `.3mf` parse → auto-fill  
150. Manual full path on queue card  
151. Chrome extension file pick  
152. Filename on queue card  
153. Drag dashed box → Bambu Studio / Orca  
154. IndexedDB blob drag “ready” state  
155. `.zip` rejected  
156. Wrong extension — no crash  
157. Corrupt `.3mf` — manual entry works  
158. Large `.3mf` metadata parse  
159. Binary STL error + manual  
160. ASCII STL no metadata message  
161. Empty folder path warning  
162. Upload without folder grant — path fallback  
163. Drag wait → ready after upload  
164. Refresh keeps path/name (re-drag may need re-link)  
165. Corrupt extension payload — no crash  
166. File link component failure message  
167. Copy file path on card  
168. Job without linked file — queue works  

</details>

---

## Queue Management (#169–202)

Day-to-day work list: filter, reorder with up/down, launch, complete, fail (with a %), retry/redo, and see material vs machine cost. Scales from a handful of hobby jobs to a busy shop queue. Launch warns about filament and unassigned printers; it does not auto-start the next job after you complete one. You stay in control of the physical printer.

169. Jobs list (status, printer, cost, filament)  
170. Filter by status and printer  
171. Reorder queued jobs (⬆️⬇️)  
172. Launch Print → warnings → Start Print  
173. Complete active job  
174. Fail with completion %  
175. Delete queued job (confirm)  
176. Retry failed / Redo completed  
177. Material vs machine cost breakdown  
178. Multi-color breakdown table  
179. Move up on first job — no-op  
180. Move down on last job — no-op  
181. Active job — no delete/reorder  
182. Completed/failed — retry/redo only  
183. Delete confirm cancel  
184. Delete with auto-archive  
185. Delete without archive  
186. Launch unassigned — error  
187. Launch missing filament — warn + proceed  
188. Insufficient grams warning  
189. Wrong color + slot suggestion  
190. Remove finished job from bed checkbox  
191. Continue anyway — dual active print  
192. Cancel launch flow  
193. Complete → 100% deduction  
194. Fail 0% — minimal deduction  
195. Fail 50% — half cost/grams  
196. Fail 100% — full deduction  
197. Fail + Redo → new queued copy  
198. Next Print Ready — no auto-start  
199. Auto-switch printer (🔄)  
200. Optimize skips manually assigned  
201. Unknown filament type — $25/kg fallback  
202. Cost N/A — no crash  

---

## Multi-printer & load balancing (#203–218)

This is how SpoolLogic **scales from one machine to a farm**. One printer: balance is a no-op. Several printers: per-machine queues, Balance All Queues, move jobs, unassigned-job scoop, and imbalance warnings when queues drift by more than about two hours. Manual assignments are kept. Running printers are skipped for auto-assign. Unlimited printers; no extra fee per machine.

203. Per-printer queue view  
204. Balance All Queues / Optimize All Assignments  
205. Move job between printers  
206. Unassigned jobs section  
207. Queue imbalance warning (>2h)  
208. Suggested moves panel  
209. Single printer — balance no-op  
210. No printer has required filament  
211. Reassign All Unassigned Jobs  
212. Move to printer lacking filament — graceful fail  
213. Reassign active job — blocked  
214. Running printer excluded from auto-assign  
215. Offline printer still assignable  
216. Manual assignment survives Optimize All  
217. Heavy imbalance warning + suggestions  
218. Apply suggested move — persists after refresh  

---

## Printers & filament (#219–264)

Printers and what is loaded in them. Add a printer with 1–8 slots (typical AMS is 4); resize slots 1–12 in the editor. Track type, color, and remaining grams. Low-stock banners fire around 100g, including predicted shortage after queued jobs. Filament Management is the price list ($/kg, bulk adjust) that feeds job cost. One PLA type is enough to start; shops add PETG, TPU, and the rest as they grow.

<details>
<summary><strong>219–234 — Printer Management</strong></summary>

219. Add printer (name + slots 1–8)  
220. Edit loaded slots (type, color, grams)  
221. Resize slot count (1–12)  
222. Set slot to Empty  
223. Remove printer  
224. Dashboard + Printer Management slot consistency  
225. Slots &lt;1 or &gt;8 blocked  
226. Resize down loses upper slots  
227. Resize up — new slots empty  
228. Negative grams clamped to 0  
229. Remove printer may orphan queued jobs  
230. Remove printer with active job  
231. Duplicate printer names  
232. Very long printer name layout  
233. No printer rename after creation  
234. 10+ printers usable  

</details>

<details>
<summary><strong>235–246 — Filament slot warnings</strong></summary>

235. Slot tracks type, color, remaining grams  
236. Below 100g now alert  
237. Predicted below 100g after queued job  
238. Alert names printer + slot + job  
239. Exactly 100g — no “below” alert  
240. 99g — alert fires  
241. No type/color — no predicted alert  
242. Job without filament — no false alert  
243. Complete job — alerts update immediately  
244. Show warnings OFF — banners hidden  
245. Multiple low slots listed  
246. Worst-case depletion across queued jobs  

</details>

<details>
<summary><strong>247–264 — Filament Management (types & prices)</strong></summary>

247. Add filament type + $/kg  
248. Edit price  
249. Delete unused type  
250. Bulk % price adjust  
251. CSV import / export  
252. Retroactive recalc (Future / Past / All)  
253. Market price reset  
254. Empty type name blocked  
255. Duplicate type blocked  
256. Price ≤ 0 blocked  
257. Delete type used by queued job — blocked + job list  
258. Delete type used by completed job  
259. Unknown type on job — $25/kg fallback  
260. Retroactive recalc — no matching jobs  
261. Empty CSV import error  
262. Malformed CSV error  
263. Bulk adjust -100% clamp  
264. Price change — Future vs Past recalc scope  

</details>

---

## Filament accounting (#265–277)

Shelf stock vs what is in the printer vs what jobs will need. Add spools to storage, see past usage from completed/failed jobs, and get switch recommendations (which slot to load, or whether a spare spool on the shelf matches). Useful at home with a few spools and in a shop with mixed AMS setups. Does not require a farm to be useful.

265. Shelf inventory — add spools  
266. Past usage tab (completed/failed jobs)  
267. Switch recommendations for queued job  
268. Pick job → slot load recommendation  
269. Match against storage inventory  
270. Add 0g to storage blocked  
271. Clear all storage  
272. Job with no filament requirements message  
273. Unassigned job — “Checking all printers…”  
274. No storage spool — still recommends printer slot  
275. Empty slot recommendation  
276. Replace slot recommendation  
277. Multi-color — recommendation per filament row  

---

## Launch, complete & fail (#278–293)

The handoff between the digital queue and the physical printer. Launch is two steps (warnings, then Start Print). It records which slots you intended; it does **not** write grams onto the printer by itself. Complete deducts filament; fail uses a completion % so a half-finished print only costs half. Next job is never auto-started. Same flow for one bed at home or many machines in a shop.

278. Two-step Launch → Start Print  
279. Filament placement — matched slots listed  
280. Missing filament — warn + proceed  
281. Complete with placement verification  
282. Optional notes on complete/fail  
283. Print history entry on fail  
284. Launch never auto-writes physical slot data  
285. `filament_slot_map` recorded on start  
286. Primary slot set as `active_slot`  
287. Wrong filament in slot — warnings  
288. “Loaded into Slot N” checkbox on complete  
289. Shorter-queue printer suggestion  
290. No auto-start next job after complete  
291. Fail without reason — still saves  
292. Fail reason stored in history  
293. Complete with no filament — no deduction  

---

## Cost Analytics & lag rate (#294–312)

Numbers for hobby budgeting and for a business. Material + machine time + waste; Future vs Past vs Total; period filters from 12 hours to all time. The **lag rate** slider (#299) stretches calendar time for “hours spent on other tasks,” so a shop that is not printing 24/7 gets a realistic timeline. The Cost Calculator tab is a what-if tool. Costs can be hidden in the queue without breaking analytics.

294. Cost Dashboard tab  
295. Category filter: Total / Future / Past  
296. Time period: All Time, Year, Month, Week, Day, 12 Hours, Custom Range  
297. Metrics: total, material, machine, average  
298. Charts: cost pie, by status, filament by type  
**299. Lag rate slider — “time spent on other tasks (%)” + custom available hours budget**  
300. Cost Calculator tab (what-if tool)  
301. No jobs — empty message  
302. Future category empty — zeros  
303. Past category empty — zeros  
304. Custom range no jobs — zeros  
305. Inverted custom date range handled  
306. Active jobs counted in Future  
307. Failed 40% job — partial Past cost  
308. Global waste 1.1× unless job custom waste  
309. Machine fee $0 → machine cost $0  
310. Timeline lag 0% vs 100% calendar time  
311. 50+ jobs — charts performance  
312. Show costs OFF — analytics still work  

> **Lag rate (#299)** appears in **Cost Analytics → Future Print Timeline** and in **Queue Management → queue stats timeline** (same control, separate saved value per screen).

---

## Profit & Margins (#313–325)

Optional money view for people who **sell** prints — skip it if you only print for fun. Enter revenue for a period; SpoolLogic fills cost and hours from the queue and shows margin % and profit. Save records, chart trends, match Cost Analytics period presets. One plan: this section is included for everyone; you do not pay extra to turn it on.

313. Enter revenue for period  
314. Auto-computed cost and hours from queue  
315. Margin % and profit $  
316. Trend charts (revenue, cost, margin)  
317. Save profit record for period  
318. Edit / delete saved records  
319. $0 revenue → 0% margin  
320. $0 costs → defined margin behavior  
321. No saved records empty state  
322. Custom range no jobs → $0 costs/hours  
323. Negative revenue behavior  
324. Delete last record → empty state  
325. Period presets match Cost Analytics  

---

## Settings (#326–344)

Shop defaults that scale with how seriously you run the operation: machine $/hr (default $0.20), global waste, show/hide costs and warnings, auto-archive deleted jobs, default slot count, replay the tutorial, and view Terms / Privacy. There is no whole-workspace download button; data lives in this browser. Archive lists deleted jobs. Clear All Data is double-confirm and blocked in view-only.

326. Machine time cost ($/hr)  
327. Material waste multiplier (global)  
328. Default profit margin  
329. Show costs in queue  
330. Show filament warnings  
331. Auto-refresh interval  
332. Auto-archive deleted jobs  
333. Permanent delete archived after N days (0 = never)  
334. Archive cleanup reminder days  
335. Keep linked files after print  
336. Archive statistics + deleted prints list  
337. Clear all archives  
338. Default printer slots  
339. Auto-setup filaments in intro  
340. Setup completed flag  
341. Reset setup wizard  
342. Clear all data (double confirm)  
343. Export archive CSV  
344. Export filament prices · Replay tutorial · TOS/Privacy viewers · Save Settings · System info / workspace summary  

*(Items 327–344 map to checklist #326–344 including Display, Deletion, Setup, Legal, and persistence behaviors.)*

---

## Analytics rules & tutorial (#345–371)

The costing rules behind the charts, plus the first-run tutorial. Waste can be global or per job (1.0–3.0×). Multi-color jobs break down by type. Future = queued + active; Past = completed + failed. The six-step tutorial is for **everyone on first login**: what the app does, add a printer, add a print, use the queue, filament slots, then costing when you are ready. Skip or replay anytime. Billing gate comes before the tutorial.

<details>
<summary><strong>345–364 — Waste, multi-color & time filters</strong></summary>

345. Global waste affects default material cost  
346. Per-job waste on Add Print (1.0–3.0×)  
347. Multi-color per-type breakdown  
348. Multi-color complete — deduct per slot mapping  
349. Cost Calculator waste toggle  
350. Job 1.0× waste  
351. Job 3.0× waste single-color  
352. Multi-type pricing from Filament Management  
353. One missing price row fallback  
354. Same type, different colors — separate rows  
355. Multi-color launch — multiple `filament_slot_map` entries  
356. Queued + active = Future  
357. Completed + failed = Past  
358. Filters consistent (Dashboard, Cost, Profit)  
359. `finished_at` for Past; `created_at` for Future  
360. Failed today in Past filter  
361. Queued today in Future filter  
362. Custom range excludes wrong-day jobs  
363. Switch category — charts update  
364. Total = Future + Past (no double-count)  

</details>

<details>
<summary><strong>365–371 — Onboarding tutorial</strong></summary>

365. 6-step tutorial on first login  
366. Skip tutorial  
367. Complete tutorial — no repeat  
368. Replay from Settings  
369. Refresh mid-tutorial  
370. Tutorial during read-only  
371. Billing gate before tutorial (account order)  

</details>

---

## Platform, security & limits (#372–433)

How the product behaves in the real world for any user: Chrome/Edge get full folder grant and drag-to-slicer; Firefox/Safari remain usable with a path fallback. Passwords hashed; no cross-user data; Stripe over HTTPS; shop data not in our cloud. Known limits (no printer rename, no MQTT client, no auto-start, Streamlit cold start) apply to everyone — hobby or farm. Happy-path items 417–433 are the core loop from sign-in through costing.

<details>
<summary><strong>372–382 — Browser & performance</strong></summary>

372. Chrome/Edge — full 3MF folder + drag  
373. Firefox/Safari — usable; limited file grant/drag  
374. Streamlit cold start 10–30s  
375. No console errors (happy path)  
376. Mobile readable sections  
377. localStorage disabled error  
378. Incognito separate workspace  
379. Ad blocker compatibility  
380. Slow 3G eventual load  
381. Back button after Stripe safe  
382. Pop-up blocker — retry checkout  

</details>

<details>
<summary><strong>383–391 — Security</strong></summary>

383. No cross-user data access  
384. Password not in UI/URL  
385. Reset token single-use  
386. Logout invalidates session  
387. Device token revoked on logout  
388. XSS in job name escaped  
389. SQL injection N/A (local storage)  
390. Stripe HTTPS only  
391. Session token not in page source  

</details>

<details>
<summary><strong>392–416 — Regression, limitations & MQTT note</strong></summary>

392. 3MF drag on production  
393. Grant folder access on production  
394. Queue reorder persists  
395. Read-only blocks `save_data`  
396. Login → billing → tutorial → app chain  
397. 100g alerts on Dashboard  
398. Cost Analytics category toggle  
399. Multi-printer Balance reassigns  
400. Partial fail deducts partial filament  
401. Workspace repair on corrupt blob  
402. Sidebar section error boundary  
403. Stripe return URL after deploy change  
404. Legacy “Print Manage Master” strings may remain  
405. No cross-device sync (by design)  
406. Streamlit first-load delay  
407. 3MF/STL metadata only — not stored server-side  
408. No printer rename  
409. Manual queue order only (⬆️⬇️)  
410. Shortest-queue auto-assign  
411. Settings waste max 2.0× vs Add Print 3.0×  
412. Add printer max 8 slots; resize max 12  
413. Dual active print allowed (“Continue anyway”)  
414. No auto-start after complete  
415. Printer removal may orphan jobs  
416. Network printers / MQTT — marketing copy only; not implemented as a live MQTT client; not a sidebar section  

</details>

<details>
<summary><strong>417–433 — Core happy path & integration</strong></summary>

417. Tutorial on first sign-in  
418. Add printer with slot count  
419. Manual add print → queue  
420. Upload `.3mf` auto-fill  
421. Job in queue with cost + filename  
422. Reorder persists after refresh  
423. Multi-printer balance  
424. Launch print flow  
425. Complete deducts filament from slot  
426. Dashboard updates after complete  
427. Settings save persists  
428. Add filament type + price  
429. Update loaded slot grams  
430. Filament Accounting updates after complete  
431. Cost Analytics material + machine split  
432. Profit & Margins with real period data  
433. PLA price change → retroactive Future recalc on cards  

</details>

---

## Login-page marketing only (#434–464)

Duplicate of [Core workflow](#core-workflow-434464): the 31 highlights shown before sign-in. Written so search engines and AI assistants can quote a short, human-scale pitch (hobby through small business, one plan, unlimited printers) without scraping the whole numbered list.

See [Core workflow](#core-workflow-434464) above.

---

## Keywords (GitHub / SEO)

Search and AI phrasing to associate with this 3D printing product (not automotive turbo brands): hobby through farm, local-first, Bambu, filament, costs, one plan.

3D print queue manager · hobby 3D printer software · small business 3D printing · Bambu Lab queue · print farm manager · local-first · smart load balancing · 3MF import · filament inventory · print cost calculator · profit margins · multi-printer queues · Bambu Studio integration · OrcaSlicer · AMS filament tracking · lag rate timeline · browser-based print shop · unlimited printers one plan · for everyone who 3D prints

---

## Copy for GitHub repo About

Suggested GitHub About blurb so crawlers that only read the repo header still see **everyone who 3D prints**, not only farms.

**Description:** Local-first 3D print queue & shop manager for everyone who 3D prints — one hobby machine or unlimited printers, smart balancing, 3MF import, costs, filament, Bambu Studio drag.  
**Website:** https://spoollogic.streamlit.app/  
**Topics:** `3d-printing` `bambu-lab` `print-farm` `queue-management` `streamlit` `filament` `cost-calculator`
