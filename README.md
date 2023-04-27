# Mojang API

This type script module allows you do download skins and capes from Minecraft Players using [api.mojang.com](https://api.mojang.com/)

```ts
import { getUser, getProfile, getTextures, getSkin, getCape } from "./index.js";

const [skin,cape] = await getUser("Offroaders123")
  .then(getProfile)
  .then(getTextures)
  .then(textures => {
    if (textures === null){
      throw new Error("No textures were found for this player!");
    }
    return Promise.all([
      getSkin(textures),
      getCape(textures)
    ]);
  });
  ```
  
  ---
  
  For more information please visit: [wiki.vg/Mojang_API](https://wiki.vg/Mojang_API)
  
