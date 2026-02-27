# UCSD Robocar Framework — ECE/MAE 148 Course Documentation

This repository hosts the complete setup, calibration, and development guide for the UCSD Robocar Framework used in ECE/MAE 148 (Autonomous Vehicles).

## Live Site

Hosted via GitHub Pages:  
👉 `https://<your-org>.github.io/<repo-name>/`

---

## File Structure

```
/
├── index.html          ← Main documentation site (single page)
├── images/             ← All figures — replace files here to update images
│   ├── fig_xeyes.png
│   ├── fig_hsv_chart.png
│   ├── fig_mask_default.png
│   ├── fig_mask_yellow.png
│   ├── fig_bw_calibration.png
│   ├── fig_line_calibration.png
│   ├── fig_error_threshold.png
│   ├── fig_camera_align.png
│   ├── fig_throttle_steering.png
│   └── fig_system_response.png
├── _config.yml         ← GitHub Pages config
└── README.md           ← This file
```

---

## How to Update Images

Each figure in the documentation has a labeled `images/` key shown in its caption.

**To replace any figure:**

1. Take or prepare your new screenshot/photo.
2. Rename it to exactly match the filename shown in the figure caption (e.g., `fig_hsv_chart.png`).
3. Drop the file into the `images/` folder, overwriting the old one.
4. Commit and push — GitHub Pages rebuilds automatically (< 2 min).

**To add a brand-new figure:**

1. Add your image to `images/` with a descriptive name (e.g., `fig_lidar_scan.png`).
2. In `index.html`, insert the following block where you want the figure:

```html
<!-- IMAGE REPLACE: swap images/fig_lidar_scan.png to update this figure -->
<figure data-img-key="fig_lidar_scan.png">
  <div class="fig-img-wrap">
    <img src="images/fig_lidar_scan.png" alt="Description of figure" loading="lazy">
  </div>
  <figcaption>Figure X.Y — Your caption here <span class="fig-key">images/fig_lidar_scan.png</span></figcaption>
</figure>
```

---

## Figure Index

| Key | Section | Description |
|-----|---------|-------------|
| `fig_xeyes.png` | §3 X11 Forwarding | xeyes window forwarded to laptop |
| `fig_hsv_chart.png` | §11 Color Calibration | HSV color wheel (H: 0–180) |
| `fig_mask_default.png` | §11 Color Calibration | Default mask sliders (all pass) |
| `fig_mask_yellow.png` | §11 Color Calibration | Tuned for yellow road dots |
| `fig_bw_calibration.png` | §11 Color Calibration | Noise reduction slider GUI |
| `fig_line_calibration.png` | §12 Line Calibration | Line detection view |
| `fig_error_threshold.png` | §12 Line Calibration | Error threshold red bars |
| `fig_camera_align.png` | §12 Line Calibration | Camera centerline alignment |
| `fig_throttle_steering.png` | §13 Actuator Calibration | Throttle/steering GUI |
| `fig_system_response.png` | §13 Actuator Calibration | Throttle scheduling plot |

---

## How to Enable GitHub Pages

1. Go to your repository → **Settings** → **Pages**
2. Under **Source**, select branch `main` and folder `/ (root)`
3. Click **Save**
4. Your site will be live at `https://<your-org>.github.io/<repo-name>/`

---

## Multi-Team Camera Isolation (ROS_DOMAIN_ID)

See **Section 9** of the documentation. Each team must set a unique `ROS_DOMAIN_ID` to prevent their ROS2 nodes from interfering with other teams during lab sessions.

**Team assignment table:**

| Team | Domain ID |
|------|-----------|
| Team 1 | 1 |
| Team 2 | 2 |
| Team 3 | 3 |
| … | … |
| Team 30 | 30 |

Teams set this in two places:
- The `docker run` command: `-e ROS_DOMAIN_ID=N`
- Inside the container's `~/.bashrc`: `export ROS_DOMAIN_ID=N`

---

## Contributing / Updating the Guide

1. Clone the repo
2. Edit `index.html` directly — it is a single self-contained file
3. Drop new images into `images/`
4. Push — GitHub Pages rebuilds automatically

For major restructuring, search for section IDs in `index.html` (e.g., `id="s9-domain"`) to find the right location to add or move content.

---

*UCSD Jacobs School of Engineering — ECE/MAE 148 Autonomous Vehicles*
