# Notice about the modified Baileys 7.X version

This **Baileys 7.X** build has been modified exclusively for **NAMI**.  
If you choose to use it in another bot and encounter errors, issues, or unexpected behavior, that is entirely up to your implementation.

**We are not responsible** for any problems caused by using this version in projects other than **NAMI**.

  
### Internal modifications
This version includes **direct mutex handling**, among other internal changes.

All rights remain reserved to the original maintainers who keep Baileys active.  
You can visit their official repositories here:

- **WhiskeySockets**: https://github.com/WhiskeySockets/Baileys/
- **PurpShell**: https://github.com/purpshell
- **Baileys Original (adiwajshing)**: (removed)


If you are using pre-NAMI builds or older Baileys versions adapted for NAMI, it is strongly recommended that you create your own forks.  
These older versions will be removed within **3 days**.

- **Bails**: https://github.com/ds6/bails/
- **Meta**: https://github.com/ds6/meta/


---

## Important: Baileys 7.X moved from CommonJS to full ES Modules

Since **7.X**, Baileys is now **100 percent ES Module**.  
This means:

- No more `require()`
- No more `default` imports
- No more `default: makeWASocket` style usage

---

# ✅ New ESM connection (Baileys 7.X)
```js
import { makeWASocket, useMultiFileAuthState } from 'baileys'

async function start() {
  const { state, saveCreds } = await useMultiFileAuthState('./auth')

  const sock = makeWASocket({
    auth: state
  })

  sock.ev.on('creds.update', saveCreds)
}

start()
