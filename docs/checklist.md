# Noise-Reduction Checklist
(5 steps to tell real semantic deletion from network noise)

## 1. Tight envelope (±5 seconds around the vanish)
- Exact UTC timestamp of the event
- Ping to the AI endpoint (terminal: ping grok.x.ai or chat.openai.com etc.)
- Browser dev tools → Network tab → note TLS handshake + first-byte time
- Local CPU/GPU spike? (Task Manager / Activity Monitor snapshot)

## 2. Environmental proxies (auto-logged if you ran a script, or grab manually)
- Space weather Kp index → https://services.swpc.noaa.gov/json/planetary_k_index_1_minute.json
- Power-grid frequency deviation (public 60 Hz / 50 Hz feeds)
- Global routing jitter (use any public ping service)

## 3. Control prompt (run hourly)
Send a totally safe prompt (“Tell me a joke”) through the same session and record the same envelope. Gives you baseline jitter.

## 4. Time-of-day test
Repeat your borderline prompt at 03:00, 15:00, and 20:00 local. If deletions cluster with traffic hours → environmental component.

## 5. Canary token
Copy-paste this invisible zero-width space into your prompt: ``
If the canary survives your local logs but the rest vanishes → pure semantic clamp.

After 30–50 events, drop the rows in the public sheet and we’ll all see which variables actually predict deletion.
