# Research Summary on Adding/Replacing Horses in RDR2/REDM

### 1. Adding a New Horse
   - Adding a new horse is possible.

### 2. Using a New Hash for the New Horse
   - A new horse can be created using a new hash (`metapeds.ymt` + `stream/horse.ymt`). However, this method is only partially functional. For example, the horse’s reins will appear invisible.

### 3. Adding a New Horse via an Outfit for an Existing Horse
   - Another approach is to add a new horse through an outfit for an existing horse (`stream/horse.ymt`). In this case, the horse works properly, but it must be spawned as an existing horse with a new outfit applied.

### 4. Replacing Horse Textures
   - Horse textures can be replaced by simply adding `.ytd` files to the `stream/` folder in your server's resource directory.

### 5. Adding New Textures in RedM
   - Adding new textures is currently broken in RedM, though there is a workaround. However, this workaround is a bit clunky and requires either a launcher that modifies client files on your server or for players to manually apply the changes (which may be unreliable).

   - **To make new horse textures work in RedM**:
     - Take the in-game file `assets_albedo.ymt`, add the new texture to it, and then place this file in the client files at:
       ```
       RedM\RedM.app\citizen\platform\packs\base\data\metapeds\assets_albedo.ymt
       ```
     - Additionally, you’ll need to add the `.ytd` file to the `stream/` folder in your server resource, as you would when replacing textures.

### 6. On the Issue with Adding New Textures
   - The file `assets_albedo.ymt` can be partially loaded via the server resource by using `METAPED_ASSETS` in `fxmanifest.lua`. However, this method is also broken; for instance, all textures except the newly added one might disappear. Attempts to keep only the new texture in `assets_albedo.ymt` do not work at all.

## RU

```
Итоги исследования замены/добавления лошадей в RDR2/REDM

1. Добавить новую лошадь можно.

2. Новая лошадь может быть сделана через новый хаш (metapeds.ymt + stream/horse.ymt).Но этот способ полурабочий. Например, поводья лошади будут невидимыми.

3. Другой способ - добавление через outfit для уже существующей лошади (stream/horse.ymt). В данном случае с лошадью всё хорошо, но спаунит её нужно через существующую лошадь + устанавливать новый outfit.

4. Текстуры лошадей могут быть заменены
- Для этого просто закидывайте .ytd в папку stream/ в ресурсе вашего сервера.

5. Добавление новых текстур в RedM сломано, но способ как этого достичь есть, хотя он костыльный и будет работать только если на вашем сервере стоит лаунчер который будет подменять клиентские файлы или же игроки сами будут это проделывать (что сомнительно).

- Для того, чтобы новые текстуры лошадей работали в RedM, нужно взять внутригровой файл assets_albedo.ymt и прописать там новую текстуру. После нужно закинуть этот файл в клиентские файлы игрока - RedM\RedM.app\citizen\platform\packs\base\data\metapeds\assets_albedo.ymt
- И нужно добавить .ytd в папку stream/ в ресурс вашего сервера, так-же как при замене текстур.

6. На счёт сломанности добавления новых текстур, assets_albedo.ymt частично можно загрузить через ресурс сервера с помощью METAPED_ASSETS в fxmanifest.lua, но как я уже упомянул - этот способ сломанный. Например, пропадут вообще все текстуры кроме новой добавленной. Ещё я пробовал в assets_albedo.ymt оставить только новую текстуру - этот способ вообще не работает.
```