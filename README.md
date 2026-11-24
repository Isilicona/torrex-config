# Eventos de TorreX sin actualizar la app

El juego descarga al abrirse:

**https://isilicona.github.io/torrex-config/eventos.json**

Si lo encuentra y es válido, lo guarda en el móvil (sirve también sin internet) y
usa sus eventos. Si no, usa los eventos de serie de la app.

## Puesta en marcha (una sola vez)

1. En GitHub crea un repositorio **público** llamado `torrex-config`.
   (El repositorio TorreX es privado y GitHub Pages gratis solo publica
   repositorios públicos; así el código del juego sigue siendo privado.)
2. Sube a ese repositorio el archivo `eventos.json` de esta carpeta.
3. En `torrex-config` → **Settings → Pages** → *Source: Deploy from a branch* →
   rama `main`, carpeta `/ (root)` → **Save**.
4. En 1-2 minutos el archivo estará en la dirección de arriba.

## Cambiar un evento

Edita `eventos.json` en GitHub (icono del lápiz) y guarda (*Commit changes*).
Los jugadores lo reciben la próxima vez que abran el juego (puede tardar unos
minutos por la caché).

```json
{
  "version": 1,
  "skins": [
    {"id": "ev_duende", "name": "Duende", "body": "#22c55e", "belly": "#fde68a",
     "pattern": "stripes", "hat": "santa"}
  ],
  "events": [
    {"id": "invierno", "name": "Navidad Helada", "start": "2026-11-01", "end": "2027-01-31",
     "color": "#38bdf8", "goal": 3, "skins": ["ev_reno", "ev_duende"]}
  ]
}
```

### Eventos (`events`)

| Campo | Qué es |
|---|---|
| `id` | Identificador. Si cambia, el contador de victorias del evento vuelve a 0. |
| `name` | Nombre que se ve en el menú (máx. 28 letras). |
| `start` / `end` | Fechas `AAAA-MM-DD` (incluidas). Fuera de esas fechas se usa el evento de serie. |
| `color` | Color de la tarjeta, por ejemplo `#38bdf8`. |
| `goal` | Niveles a ganar para la 1.ª skin (la 2.ª, el doble). |
| `skins` | Exactamente 2 ids de skins: de la app o del apartado `skins`. |

### Skins de evento (`skins`)

- `id` debe empezar por `ev_` y no repetirse.
- `body`, `belly`: colores `#RRGGBB`.
- `pattern`: `none`, `stripes`, `dots`, `stars`, `hearts`, `spots`, `zigzag`, `flames`, `split`, `mask`.
- `hat`: `none`, `bow`, `tophat`, `wizard`, `party`, `cat`, `bunny`, `flower`, `viking`, `santa`,
  `propeller`, `cowboy`, `unicorn`, `ninja`, `pirate`, `leaf`, `cap`, `headphones`, `chef`,
  `antenna`, `crown`, `horns`, `halo`, `beanie`, `astronaut`, `graduation`, `dino`, `mushroom`, `sombrero`.
- Máquina (opcional): `"style"`: `robot`, `mecha`, `car`, `truck`, `rocket`, `ufo`, `tank`, y `"glow"`: color de las luces.

Una skin con un estampado, gorro o máquina que no exista se ignora, y el evento
que la use también (para no romper el juego). Los dibujos nuevos sí necesitan
actualizar la app.

### Skins de serie que ya existen para eventos

`ev_reno`, `ev_copo` (Navidad), `ev_flor`, `ev_mariposa` (Primavera),
`ev_surf`, `ev_helado` (Verano), `ev_calabaza`, `ev_fantasma` (Halloween).
