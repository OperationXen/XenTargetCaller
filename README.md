# XenTargetCaller
A WoW plater mod to assist in battleground target calling.

1. Install the plater addon
2. Import the mod by pasting in the import string to the import menu
3. Use the targeting macro to set primary and secondary targets for everyone in your group / raid or battleground

# Import string

TN1)VPnou8)x4NGtuusiqivQ)ahDTLER0Qz6DN06mjnXarleh540TUPJ)2VNTtGabwOQDst3H8pWlXVV(Xp)8ZbSoEmgPJr)njAPZyx2mcFPZa3WqcdJ4phtWO5u6NXO2yuFF)LoUlDEKY8jmGKrtJGxXNtw64LYyKiqyUujTWid8O2ADT71ZgJ6GhP3vZ0YstZ2cJmXOHFlyb1NCs)VXCdPryKfWcg1fpYWc4Ww4xJCxqIdD5G6bBt8XOPPrE8ak4R1tiHtBU0jnkGp0pJ4cgibqtIEAS7JHcsWisYglVEPJAmlna86Zw6CpiYL3p886kLuGL1ubtxjWzR1wRywWcx2ZYGpQGCzJvotlayhp43D9(8mjA16jcJt(QhnKYK(qURQy8oLAxZ)aGXu2lWaNcRxFPEHqHeMqEjYFvGpzd5HL4dhxsiE0i)FcidkxX)cJnWJy0DHUpl2D8E6mrADHm2DKkEYjbrjqCd7FGndlDMtyfCOYzBaSuR2oyOaSVflRPw7jRe7DpbBzVYnYh2UNVHIiEh8BRwTAugBel7soo7SAdUQ)4j3GUCs)Zp)2r123kE(ibGhIAPfmfXJxxFVMPO5wjNiYKRivAQ8HQw0KeoliAwrlBuPL3sfXmY0GVQubNLK(y9n0nOo9MghU6wvcApkR9bOkb2ST3jGO7o5GXNFyIwrx9G1KWP2zw5wk8f6GvNWxkDVQXM7D3htqbI9HZOxboVP7)6r61RBVX48wvE(jHYIUiknU(qy)6FOb34HvX0nKKe3zezjEzGTNzeNdnGrG(pKVOETl(q)BExTgvOYt)azwqcNWKvxRVDzYcINK65bck9Hbtgm3LpmAkTvU8qpp0OmnFNmZREw9VkDbeHJ8ybXG5Vns6h1AUN6(nYo3QqZw3h7d)(w1U1HFC6)ZAm7)YnwvQXi4XSbgnGgbN0L6XPS3OCSndP1o2yYx5PmYzF8JdJGDutD9ipaBRUnk5H7e56Shwq8dCFywi9ltyUaz4eDJEF6tvR6RibZMZLa6ACrQu1wWljCfl1B8BlDmQwH)vGpF(puFsoay2rOWwD2v2ZHL1Urrpy5FAWS8not82AX)qZw2LoxL0wsRvdh9J8MNLW(9YPIjb(QA32nlpPQpnTDmZZLM5F2Xrjvx6ARLPsZkCCvc2PQtqgUaQnxFxlSqcnxLL2SICJMvLmcmuJc72HBGu7qka3kZW7OQqPTqRvNkUAbhXKVevFVwOzvRVn2O4ag9EQlaFWzxeYXlpD8YthV80XlpD8YthV80V4xEIJr9eFWAUBimhqbVqCkxSI0l0njrrUWnEsGF2dmODufv8tXfLnjM4POCNcEUIKe5bNBcHwbfqdvkaO5up4O)e4mk8iBnnnDqybgi)IKCXNZNglobti6i5N9FS4Z7l(O7IR(bSLNTU6Vbq2Zgg9NUHPeLuxyPzBBzB0UtBR2wA6w4PN0PnEKb(IoD7O3XQRMMHTLPLPMyME4rWKA4rMcHbN8pipdb7gDAIrd9eE5(Aqpq05uYdkNxkdiY5KepiaK)XdzTFYPqNojWlMks9wFnqzWa2g8XYXmADPevuVz02ZuRRLUDBnttdtBJUfIwZ22Dn1T1m61TTEpjoykI2lm7yOB0vRNMrBlbujMXAley7(IFfyqE330Pz)rmZHobdvxnrIeYxw82J5aIyG)3d

# Primary Target Macro

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

