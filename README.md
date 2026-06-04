# Mi Ahorro · Android App

Esta versión convierte el MVP web de finanzas en una app Android con Capacitor.
No se abre como navegador: se instala como APK, con ícono propio y pantalla de inicio.

## Opción rápida: compilar desde GitHub Actions

1. Subí todo este proyecto a un repo de GitHub.
2. Entrá al repo > Actions.
3. Abrí el workflow **Build Android APK**.
4. Tocá **Run workflow**.
5. Cuando termine, descargá el artifact **mi-ahorro-debug-apk**.
6. Instalá el APK en Android.

## Opción local con Android Studio

Necesitás Node.js y Android Studio.

```bash
npm install
npx cap add android
npx capacitor-assets generate --android
npx cap sync android
npx cap open android
```

En Android Studio podés tocar **Run** para probar o **Build > Generate Signed Bundle / APK** para Play Store.

## Para Play Store

Google Play pide Android App Bundle (.aab) para apps nuevas. Generalo desde Android Studio o con:

```bash
npm run android:release:aab
```

Para publicar vas a necesitar cuenta Google Play Console, firma de app y ficha de privacidad porque la app guarda datos financieros del usuario en Supabase.

## Supabase

La app ya conserva la conexión del MVP actual. Si tenés confirmación por email activada, el usuario puede verificar desde el navegador y luego volver a iniciar sesión en la app.
