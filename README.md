Interactive Bézier Rope Simulation;

This project implements a cubic Bézier curve that behaves like a springy rope reacting to real-time user input.

Bézier Math:

The curve is computed using the cubic Bézier equation:

B(t) = (1−t)³P₀ + 3(1−t)²tP₁ + 3(1−t)t²P₂ + t³P₃


The curve is sampled at small intervals (Δt = 0.01) and rendered manually.

Tangents:

Tangents are calculated using the derivative:

B'(t) = 3(1−t)²(P₁−P₀) + 6(1−t)t(P₂−P₁) + 3t²(P₃−P₂)


They are normalized and drawn at fixed intervals along the curve.

Physics Model:

Control points P₁ and P₂ use a spring–damper system:

acceleration = -k(position − target) − damping * velocity


This produces smooth, rope-like motion.

Interaction:

Mouse movement updates target positions for the control points. Motion is updated every frame using requestAnimationFrame to maintain ~60 FPS.
