# Photocraft Flatpak Wayland Fix

Dieses Repository bietet eine schnelle Lösung für Grafik- oder Performance-Probleme mit **Photocraft** (`ai.storyteller.photocraft`) unter Linux-Systemen, die **Wayland** nutzen.

## 🛠️ Das Problem

Auf einigen Linux-Distributionen mit Wayland kann es bei der Flatpak-Version von Photocraft zu Darstellungsfehlern, Skalierungsproblemen oder Abstürzen kommen, da die App nativ unter Wayland eventuell noch nicht stabil läuft.

## 🚀 Die Lösung (X11-Modus erzwingen)

Du kannst die App dazu zwingen, über den X11-Kompatibilitätsmodus (**XWayland**) zu laufen. Öffne dazu einfach dein Terminal und führe folgenden Befehl aus:

```bash
flatpak override --user --nosocket=wayland --socket=x11 ai.storyteller.photocraft
```

Dadurch werden der App die Wayland-Rechte entzogen und stattdessen die X11-Verbindung erlaubt. Der Befehl gilt nur für deinen aktuellen Benutzer (`--user`) und benötigt keine Root-Rechte.

## 🔄 Rückgängig machen

Falls du die Änderung später wieder zurücksetzen und Photocraft wieder nativ unter Wayland starten möchtest, nutze diesen Befehl:

```bash
flatpak override --user --reset ai.storyteller.photocraft
```
