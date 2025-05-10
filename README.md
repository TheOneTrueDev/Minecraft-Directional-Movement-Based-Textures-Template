# Minecraft-Directional-Movement-Based-Textures-Template


# 🎮 Dev's Directional Movement Based Textures Template (Minecraft Resource Pack)

This is a **template resource pack** for Minecraft that allows item textures to dynamically change based on **player key input** — such as movement keys or sneaking.  
It leverages Minecraft’s **model predicate system** (`minecraft:condition` and `keybind_down`) introduced in 1.20.5+ snapshots.

---
 <summary><strong>📁 Directory Structure</strong></summary>

<pre>assets/
└── minecraft/
    ├── items/
    │   └── bucket.json                         <- Main model that loads conditionally
    ├── models/
    │   └── custom_item_models/
    │       └── bucket/
    │           ├── forwards.json
    │           ├── backwards.json
    │           ├── left.json
    │           ├── right.json
    │           ├── sprinting.json
    │           ├── sneaking.json
    │           └── still.json                 <- Sub-models per movement key
    └── textures/
        └── item/
            └── custom_item_textures/
                └── bucket/
                    ├── forwards.png
                    ├── backwards.png
                    ├── left.png
                    ├── right.png
                    ├── sprinting.png
                    ├── sneaking.png
                    └── still.png             <- Custom textures linked to sub-models
 </pre>
</details>


---

## 🛠 How It Works

- The `item/bucket.json` model is the **entry point**, rename this to whatever item you want to edit.
- It uses nested `minecraft:condition` logic to detect **active keybinds** like:
  - `key.forward`, `key.back`, `key.left`, `key.right`, and `key.sneak`.
- Based on the key pressed, it loads a different model from `custom_item_models/bucket/`, which links to a texture in `custom_item_textures/bucket/`.
- It can detect the sneak key, the sprint key and the directional keys.
- The sneak texture overwrites all others then the sprint texture overwrites the rest followed up by the cardinal directions.

---

## ✏️ How to Customize

1. **Use a Different Item**  
   - Copy and rename `bucket.json` to another item path (e.g. `carrot_on_a_stick.json`).
   - Update paths inside the file to match your new model/texture folder.

2. **Add More Folders for Modular Support**  
   - Create new folders under `custom_item_models/` for each item type (e.g., `sword/`, `shield/`).
   - Each folder can contain unique movement-based sub-models.

3. **Link Your Own Textures**  
   - Change the `textures.layer0` property in each sub-model (`left.json`, `right.json`, etc.) to use your custom textures.

4. **Add More Conditions**  
   - Include additional states like `key.use`, `key.jump`, etc., by expanding the logic tree in the main `.json`.

5. **Use Misode's Item Generator**  
   - (https://misode.github.io/assets/item/).
   - Copy and paste the contents of `bucket.json` to the bottom right of the website and easily edit the json.
   - Donate to Misode cause they're cool. (https://ko-fi.com/misode)

---

## ⚠️ Limitations

- **Experimental Feature**:  
  This uses features only available in Minecraft **1.20.5+**.

- **Client-Side Only**:  
  It works based on local **keybind inputs**, not actual movement, velocity, or server-side conditions.

- **One Input at a Time**:  
  The system processes inputs **sequentially**, so combining multiple simultaneous key presses is complex without deep nesting.

- **Keybinds Only**:  
  Only supports detecting keys like:
  - `key.forward`, `key.back`, `key.left`, `key.right`, `key.jump`, `key.sneak`etc.
  - It does **not** detect mouse movement or other conditions.

---

## ✅ Great For

- Tools that visually indicate player movement.
- Gadgets or accessories with reactive visuals.
- Animated HUD-style items (compass-like behavior, indicators, etc.).

---

## 📌 License

You may use this template freely. Attribution is appreciated but not required unless otherwise stated.

---

## 🔗 Links


1. **My other packs**  
   - CurseForge (https://www.curseforge.com/members/theonetruedev/projects)
   - Modrinth (https://modrinth.com/dashboard/projects)

1. **Donations <3**  
   - <3 (https://buymeacoffee.com/theonetruedev)
---
