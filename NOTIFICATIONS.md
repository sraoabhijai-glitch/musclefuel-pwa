# Notification behavior and iPhone setup

Version 1.3 supports notification reminders **while MuscleFuel is open and running**. This is NOT server-backed Web Push. Do not rely on it to remind you when the app is closed, suspended, or the phone is locked.

1. Host the PWA on HTTPS (GitHub Pages).
2. On iPhone, open it in Safari, Share > Add to Home Screen, and launch from the Home Screen.
3. In Settings, enable reminders and allow notifications when prompted.
4. Set the reminder lead time and save. Test using the test button.
5. Keep the app open for in-app scheduled reminders. iOS may suspend it when backgrounded.

## True background push (future integration)

To deliver reliable closed-app reminders, add a backend scheduler and Web Push subscription service. The backend must store PushSubscription endpoints securely, use VAPID signing, and schedule notifications for each user's configured time zone. This cannot be implemented solely with a static GitHub Pages site. Never put private VAPID keys or server credentials in client JavaScript or the GitHub repository.

## Data

Settings are saved in the same local browser storage as meal tracking. Export JSON before upgrading. Reminders are local to the installed device and not synced.
