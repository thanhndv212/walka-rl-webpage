# Walka RL Mjlab Webpage

Project webpage for [walka_rl_mjlab](https://github.com/thanhndv212/walka_rl_mjlab) — bipedal locomotion via reinforcement learning on the Walka humanoid robot.

## Live Site

- **Production**: [https://thanhndv212.github.io/walka-rl-webpage/](https://thanhndv212.github.io/walka-rl-webpage/)
- **Local preview**: Open `index.html` directly in a browser

## Structure

```
walka-rl-webpage/
├── index.html           ← main page
├── README.md            ← this file
└── static/
    ├── css/             ← Bulma + custom styles (copied from soarm-ws-webpage)
    ├── js/              ← Bulma carousel, slider, FontAwesome (copied from soarm-ws-webpage)
    └── images/          ← training demo GIFs (copied from walka_rl_mjlab/docs/images/)
        ├── walka_flat_trained.gif
        ├── walka_rough_trained.gif
        ├── walka_rough_stairs.gif
        ├── walka_rough_slope.gif
        ├── walka_rough_bumps.gif
        └── walka_rough_wave.gif
```

## Sections

1. **Overview** — what the project does, training setup (vast.ai RTX 4090), Walka-Flat vs Walka-Rough tasks
2. **Training Demos** — GIF showcases of trained policies on flat and rough terrain
3. **RL Training Pipeline** — task setup, observation/action spaces, reward shaping, PPO hyperparameters, rented-GPU workflow
4. **Terrain Types & Curriculum** — seven sub-terrain types in the rough curriculum, isolated per-terrain demos
5. **Reward Design** — table of all sixteen reward terms with weights, kinds, and purposes
6. **Docs & Resources** — links to `reward_design.md`, `vast_ai_training.md`, `kinematic_structure_analysis.md`, `get_up_task.md`
7. **Installation** — clone, uv sync (CPU/GPU), usage examples (train, play, keyboard-steer, push to Hub)
8. **Acknowledgements** — unitree_rl_mjlab (code structure inspiration), mjlab, RSL-RL

## Publishing to GitHub Pages

This repo mirrors the workflow used for `soarm-ws-webpage`:

1. **Create a new GitHub repository**:
   ```bash
   # On GitHub: create thanhndv212/walka-rl-webpage (public, no template)
   cd /Users/thanhndv212/Develop/webpage-ws/walka-rl-webpage
   git init
   git add .
   git commit -m "Initial commit: Walka RL Mjlab project webpage"
   git branch -M main
   git remote add origin git@github.com:thanhndv212/walka-rl-webpage.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**:
   - Go to repo **Settings** → **Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** / **/ (root)**
   - Save

3. **Wait 1-2 minutes**, then visit:
   - https://thanhndv212.github.io/walka-rl-webpage/

4. **Update main homepage** (optional):
   - Add link to https://thanhndv212.github.io under "More Research" → "Walka RL - Bipedal Locomotion"
   - Update `soarm-ws-webpage/index.html` and `walka-rl-webpage/index.html` navbar dropdowns to cross-link

## Local Development

No build step needed — pure static HTML. To preview:

```bash
open index.html   # macOS
# or serve via Python:
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Dependencies

- **Bulma CSS** (via CDN and local minified copies in `static/css/`)
- **FontAwesome** (all.min.css + JS, local)
- **Google Fonts** (Google Sans, Noto Sans, Castoro via CDN)
- **Bulma extensions**: carousel, slider (local JS in `static/js/`)

All static assets are self-contained; no npm, no build pipeline.

## License

This website is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

The GIF demos and content are derived from the [walka_rl_mjlab](https://github.com/thanhndv212/walka_rl_mjlab) repository.
