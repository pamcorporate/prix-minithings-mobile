# Stan sprites go here

The game loads five PNGs from this folder (it used to pull them from the
Supabase bucket; for the offline app they must be bundled here):

- `happy.png`  - Stan content
- `sad.png`    - Stan sad
- `sadP.png`   - Stan sad (paid/poorer variant)
- `cry.png`    - Stan crying
- `cryP.png`   - Stan crying money

Drop the five files in this folder with these exact names. The game references
them as `./sprites/<name>.png`. Once they are here, delete this placeholder.

Source: they currently live in the Supabase public bucket and on the
switchmyhouse.com.au child theme. The originals are the cleanest to bundle.
