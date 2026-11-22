# Rusty School Locker: Blender Modeling & UV Unwrapping

A beginner-friendly, low-poly school locker modeled and UV unwrapped in **Blender 5.3**. This project covers Part 1 (modeling and unwrapping). Texture painting follows in Part 2.

## Overview

| Item | Detail |
|---|---|
| Software | Blender 5.3 |
| Skill level | Beginner (basic Blender knowledge needed) |
| Approach | Model the top half, duplicate it for the bottom, then unwrap using seams |
| Real-world size | About 1.8 m tall (modeled as two 0.9 m halves) |

## Step 1: Blockout

1. Start with the default cube.
2. Open the side panel (`N` → Item) and set the dimensions for **half** the locker: **X 0.36, Y 0.46, Z 0.9**.
3. **Apply scale** (`Ctrl+A` → Scale). Without this, insets and bevels distort because of the non-uniform scale.

## Step 2: Door Detail

1. Enter Edit Mode (`Tab`), switch to Face mode, and select the front face.
2. **Inset** (`I`), then **Extrude** (`E`) outward to form the door. Adjust with `G` `Y`.
3. Inset again and extrude **inward** slightly to create the recessed door panel.

## Step 3: Vents

1. **Loop cut** across the middle (`Ctrl+R`, click, then right-click to cancel the slide).
2. Select the two faces and **inset individually** (`I`, then `I` again).
3. Scale on Z (`S` `Z`) and move them up (`G` `Z`).
4. The middle edge gets in the way. Because the surface is flat (planar), remove it with **Dissolve Edges** (not Delete, which would leave a hole).
5. Extrude the vent faces outward, then select the top edges and pull them back (`G` `Y`) and down (`G` `Z`) to create angled slats.
6. Clean up the thin triangle by sliding an edge loop (`Alt+Click`, `G` `Z`).
7. Optional: in Vertex mode (`1`), join vertices with `J` to preview the triangulation a game engine will produce.

## Step 4: Duplicate and Join

1. Select all in **Edit Mode** (not Object Mode, so everything stays one object).
2. Duplicate (`Shift+D`) along Z and move the copy down.
3. Select the two facing faces and use **Edge → Bridge Edge Loops**. This joins the halves and removes the internal faces.
4. Optional cleanup: **Merge by Distance** (`M`) on unneeded vertices.

## Step 5: Top and Bottom Trim

1. Extrude the top face up slightly.
2. Select the outer edge loop (`Alt+Click`), extrude (`E`), constrain with `Shift+Z`, and scale out (`S`).
3. Select the top face and use **Dissolve Edges** to remove unnecessary geometry.
4. Repeat at the bottom, then fine-tune with `G`.

## Step 6: UV Unwrapping

1. Mark **seams** (`Ctrl+E` → Mark Seam) to split the model into flat sections: front, back, top, bottom, and sides.
   - Use `Ctrl+Click` to select edge paths and `Alt+Click` to select edge loops.
2. Switch to the **UV Editing** workspace.
3. Select all (`A`), unwrap (`U`), and compare methods:
   - **Angle Based**: the common default, but it distorted the doors.
   - **Conformal**: gave better results on the doors, so this was chosen.
4. Set the **island margin** to 0.01 or slightly higher to avoid texture bleed between islands.

## Key Techniques and Takeaways

- **Apply scale** before insetting or beveling.
- **Work in halves.** The model isn't symmetrical, so no Mirror modifier is used. Duplicate in Edit Mode instead.
- **Dissolve, don't delete**, to remove edges without creating holes.
- **N-gons are fine on flat surfaces**; they are triangulated on export or render.
- **Test more than one unwrap method**, since results vary by shape.

## Tools Used

- Blender 5.3

## Next Steps

- [ ] Part 2: Texture painting (rust materials)

## License

Add your preferred license here (for example, CC0 or MIT).
