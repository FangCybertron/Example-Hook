# Tutorial How To Hook String

**Take A Good Look**

# How To?

**for example I will hook leak skin mobile legends**

-  **Example String** `Leak Skin
	// RVA: 0x1EEBBA4 Offset: 0x1EEBBA4 VA: 0x1EEBBA4
	public static bool IsForbidSkin(uint skinid) { }`

-  **So I Need To Hook That String** `IsForbidSkin`

-  **Add** `bool featureHookToggle = true;`

- **Add** `bool (*old_IsForbidSkin)(void *instance);'
bool IsForbidSkin(void *instance) {'
    if (instance != NULL && featureHookToggle) {
       return true;
   }
    return old_IsForbidSkin(instance);}`
    
- **Then Add** MSHookFunction((void*)getAbsoluteAddress(targetLibName, 0x1EEBBA4), (void*) IsForbidSkin, (void**) &old_IsForbidSkin);

**Compile And You Can See ^__^**

**Don't Pm To Ask**

**Use U Brain**