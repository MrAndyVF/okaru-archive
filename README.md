# okaru-archive

**English** · [Español](#español)

The archive manager of [OKARU](https://github.com/MrAndyVF/okaru) (郁): open, extract and create zip, 7z, tar and more (rar read-only), with passwords, volumes and drag and drop.

## Install

It ships in OKARU's pacman repository `[okaru]` (set up by OKARU's installer):

```sh
sudo pacman -S okaru-archive
```

## Build

It builds against OKARU's shared core, provided by the `okaru-core` package:

```sh
meson setup build && meson compile -C build
meson test -C build
# Run it with the translations from this repository:
OKARU_APPS_DIR=$PWD/apps ./build/okaru-archive
```

Translations live in `apps/archive/translations/` (English and Spanish).

## License

MIT.

---

## Español

El gestor de comprimidos de [OKARU](https://github.com/MrAndyVF/okaru) (郁): abrir, extraer y crear zip, 7z, tar y más (rar solo lectura), con contraseñas, volúmenes y arrastrar y soltar.

### Instalar

Viene en el repositorio pacman de OKARU, `[okaru]` (lo configura el instalador de OKARU):

```sh
sudo pacman -S okaru-archive
```

### Compilar

Se compila contra el núcleo compartido de OKARU, que trae el paquete `okaru-core`:

```sh
meson setup build && meson compile -C build
meson test -C build
# Ejecutarla con las traducciones de este repositorio:
OKARU_APPS_DIR=$PWD/apps ./build/okaru-archive
```

Las traducciones están en `apps/archive/translations/` (inglés y español).

### Licencia

MIT.
