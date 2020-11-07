# XenTargetCaller
A WoW plater mod to assist in battleground target calling.

1. Install the plater addon
2. Import the mod by pasting in the import string to the import menu
3. Use the targeting macro to set primary and secondary targets for everyone in your group / raid or battleground

# Import string

TN1xVjooq8Vl8u4efLecesL6dC0TT0BlTAn9UtA7AinXarBioYX0TSRo(SFJTdKabAOQDLwDhYvQtI98VFE8mJdyd8amYaJ(Bs0YrdCzti8LJ66ggsyyeFrmbJMsPFfJAGrD89xoYD5OhPmFcdiz05rWR4tjlh5nNXiraZCPqQJrM4(n0B50UTdg1e33OLULTTUHHfgb)177bZO(Kt68DMBincJSHLGrTW9nTBJroc7QV7msCOlhepOBIpgnEEKhpGc2QwcjCCTLJMhfW75NsCbd4aOjrpnW9XqbjOejz1LxVCKAmzEay1NTC09alxEFVZ1ucj3sYOcgVMHZYKw9ywWmx2cPZhLJV0XAJPoaSd6(7UEFDIeTQ)eHXjp7rdPmPnSYuvl8oLyZwFxyHZzVcfCkSF9nTCUcjmH8A4)QaFYg8dBXhoUKq8Or()eqg0kb)lm2apIrFK6cGcYJrirBeWUJiXtojikbCB44dCwy5OPewo7PyWgGkvQSJfKd13AjzuzwYA2(WtWj2RCJ8Ht7RopreVd(F961RweAe76YvC2zv6EvNbdVbD5WoNF(T9RSVn8vJeaDiQDwqvepUMXEvtE1TMpHNj3qkvvRgQurdt4SGOj51SzPAElreZiJdEwjcolz(JABiBqCg1mpCXTod0EewJdqucSzBRtar3DYbJpVyGwEt9GLKWO2zu5wc8vAGLhWxiCVSXMhD33IG8d7dNrVbCEtZ)TJ0z7BVZ48wzE(jHYIMikmU(qw(1VOc34H1(0nKKe3jezgEPJTNzeLH6Yiq7hYxOv5Ip15MpuPAjI80prMeKWjmz2vTTttMJ9K5EEaJsBO7WUtD59IgtRVIFOLhAuQKVtg5PLM)Rutar4qbOGyq93gjTJk12tE)QPLTY1R19X(W)FV626WRM()S(Y(VCFvf6lcEmDGrDPrqLU5ECk7DkgBtxkZWgqEMpNro7ZFUxeCIASRh5b4y1TrjpCNiwN9WmIFG7dtcPFBiZfidhAy2(lFPCrFfjyYuUeqZWfPqvhbVKWvlrR6VTCKz5c8Vc85tFr5jxbaZJecSEZDf9CyrTBK0d2(hhmz1bNHEBT5FOrl7sMRdAli1YHJorEttdy)rXqXKaFvUBNAfNu1NM(oMzrHz(NDukP8uxBTnvywHHRcWovvbP3mi3S2U2yHaAUkkTwjXg1klyewqfkCAp0DrLdjbC9ufVJScfocLjoLFvhkXSAlsBVAOwz7Vv3i5agbcFHOz)psNqpE7PJ3E64TNoE7PJ3E64TN(f)2tCmQT4dwZDdH5ak4fIYCXksVq3Kef5m34Hb(PpWG(rvuXpfNNxgnmDc3XGLRijrEqHtW1YeqsmXtsb0CQhu7pbQrH77ORRBamlWazrvU4Z5tJfvWeS2x(z)hi(8(Ip6U4UFWYwfTU(Nbq20gg9NUHZjkUUWw3XX2XSrZg2nS1nSXJpPzdCFt8fnB10OPDlDDthBlBlDXmTX9Hj1X9Temdg5Fqwao7gTAIr98ew5(6qpq06uYdkJxYdWY5KepWbK)WdP9FYPqRojWlglc9YUhO0zaDd2yrFgLLkr51B6TTT0BzB40q3YY0YXSvoV1QHtlldhDZ2TAy0UTyglH3EHvttdZw6T1nBylGkXm2BHaB3y8Badw1(nDC6peZuOvWq1DtKiH8L5V(4karmW)7d

# Target Setting Macro

/run a="mouseover" t=UnitGUID(a) or "" i=select(2,GetInstanceInfo()) C_ChatInfo.SendAddonMessage("XenTC", "P-"..t, i=="pvp" and "BATTLEGROUND" or "RAID")

_This version of the macro will transmit your current mouseover target as the primary target to everyone in your BG. Only people with the plater mod above will recieve the message_

/run a="mouseover" t=UnitGUID(a) or "" i=select(2,GetInstanceInfo()) C_ChatInfo.SendAddonMessage("XenTC", "S-"..t, i=="pvp" and "BATTLEGROUND" or "RAID")

_This version sets the secondary target in the same way as above_

/run a="target" t=UnitGUID(a) or "" i=select(2,GetInstanceInfo()) C_ChatInfo.SendAddonMessage("XenTC", "P-"..t, i=="pvp" and "BATTLEGROUND" or "RAID")

_This version sets the primary target, but to whatever you currently have targetted_

---

/run a="mouseover" t=UnitGUID(a) or "" i=select(2,GetInstanceInfo()) C_ChatInfo.SendAddonMessage("XenTC", "P-"..t, i=="pvp" and "BATTLEGROUND" or "RAID") if t~="" then SendChatMessage("Primary "..UnitName(a), i=="none" and "PARTY" or "INSTANCE_CHAT") end

_Will transmit the GUID of the current mouseover target to everyone in your battleground or party / raid as appropriate, and put a message into instance chat (if in an instance)_
_This version does not have any spare characters to play with sadly_

--- 

_These macros are set up for testing, they will broadcast your target selections only to yourself. Replace the placeholder name with your character's name_

/run a="mouseover" t=UnitGUID(a) or "" i=select(2,GetInstanceInfo()) C_ChatInfo.SendAddonMessage("XenTC", "P-"..t, "WHISPER", "<insertyourcharacternamehere>")

/run a="mouseover" t=UnitGUID(a) or "" i=select(2,GetInstanceInfo()) C_ChatInfo.SendAddonMessage("XenTC", "S-"..t, "WHISPER", "<insertyourcharacternamehere>")
