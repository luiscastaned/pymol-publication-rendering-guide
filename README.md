# PyMOL-publication-rendering-guide
Professional workflow for generating high-resolution, transparent, publication-quality molecular images in PyMOL.
# 📖 Overview

This repository provides a complete workflow to:

- Remove background (transparent rendering)
- Render high-resolution images
- Control shadows and lighting
- Export publication-ready PNG files
- Verify working directory

All commands are executed directly in the PyMOL console.

---

# 🎨 Remove Background (Transparent Rendering)

As described in the reference PDF :contentReference[oaicite:1]{index=1}, use:

```python
set ray_opaque_background, off
```

This activates the alpha channel and makes the background transparent during rendering.

---

# 🌫 Remove Shadows (Cleaner Publication Look)

To eliminate heavy shadows:

```python
set ray_shadows, off
```

Optional softer lighting:

```python
set ambient, 0.5
set direct, 0.5
```

For completely flat lighting (figure-style):

```python
set specular, off
```

---

# 🖥 High Resolution Rendering

Example for 3000 × 3000 pixels (as indicated in the PDF :contentReference[oaicite:2]{index=2}):

```python
ray 3000, 3000
```

You can also use standard formats:

| Format | Resolution | Aspect Ratio |
|--------|------------|--------------|
| HD | 1280 × 720 | 16:9 |
| Full HD | 1920 × 1080 | 16:9 |
| 2K | 2048 × 1080 | ~17:9 |
| QHD | 2560 × 1440 | 16:9 |
| 4K UHD | 3840 × 2160 | 16:9 |

Example 4K:

```python
ray 3840, 2160
```

---

# 💾 Save the Image

After rendering:

```python
png nombre_imagen.png, dpi=300
```

Check directory:

```python
pwd
```

This shows the current working directory where the image was saved.

---

# 🧪 Recommended Workflow for Publication Figures

```python
set ray_opaque_background, off
set ray_shadows, off
set specular, off
set ambient, 0.5
ray 3000, 3000
png image.png, dpi=300
```

---

# 🔬 Scientific Use

This workflow ensures:

- Transparent background for journals
- High DPI publication standards
- Reduced shadow artifacts
- Clean structural visualization
- Reproducible rendering parameters

---

# 👨‍🔬 Author

Luis Ernesto Castañeda Mota  
Department of Biochemistry  
CINVESTAV-IPN  

---

# 📚 How to Cite

If you use this workflow, please cite:

Castañeda-Mota, L.E.  
*PyMOL Publication-Quality Rendering Guide.*  
GitHub Repository (2026).
