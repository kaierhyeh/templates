# Playbook: Visual Parity

Pixel-perfect UI verification, responsive layout audit, and visual regression checking.

## Phases

### Phase 1: Visual Baseline & Target
1. Obtain the reference screenshot, mockup, or baseline render.
2. Identify key visual landmarks: layout grid, typography, spacing tokens, and color palette.

### Phase 2: Implementation & Rendering
1. Apply targeted CSS/HTML modifications to match the reference.
2. Render the component in the browser or headless renderer.

### Phase 3: Parity Inspection & Diffing
1. Compare the rendered output against the reference across standard viewports (Desktop, Tablet, Mobile).
2. Inspect padding, alignment, font rendering, and contrast.
3. Eliminate layout shifts or overflow bugs before concluding.
