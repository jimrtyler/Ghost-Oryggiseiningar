# 👻 Ghost Öryggiseining
**PowerShell-byggð Windows og Azure Öryggisharðnunartól**

> **Fyrirbyggjandi öryggisharðnun fyrir Windows endapunkta og Azure umhverfi.** Ghost veitir PowerShell-byggðar harðnunarföll sem geta hjálpað til við að draga úr algengum árásarvigrum með því að slökkva á óþarfa þjónustu og samskiptareglum.

## ⚠️ Mikilvægar Fyrirvörur

**PRÓFANIR NAUÐSYNLEGAR**: Prófaðu Ghost alltaf fyrst í umhverfi sem ekki er framleiðsla. Að slökkva á þjónustu getur haft áhrif á lögmætar viðskiptaaðgerðir.

**ENGAR ÁBYRGÐIR**: Þó að Ghost miði að algengum árásarvigrum getur ekkert öryggistól komið í veg fyrir allar árásir. Þetta er einn hluti af yfirgripsmikilli öryggisstefnu.

**REKSTRARÁHRIF**: Sum föll geta haft áhrif á kerfisframmistöðu. Farðu vandlega yfir hverja stillingu áður en þú settur upp.

**FAGLEG MAT**: Fyrir framleiðsluumhverfi, hafðu samband við öryggissérfræðinga til að tryggja að stillingar passi við þarfir stofnunar þinnar.

## 📊 Öryggislandslag

Lausnargjaldskerti náðu **57 milljörðum dala árið 2025**, þar sem rannsóknir benda til þess að margar árangursríkar árásir nýti sér grunn Windows þjónustu og ranga stillingar. Algengar árásarvigur eru meðal annars:

- **90% lausnargjaldskerja atvika** fela í sér RDP arðrán
- **SMBv1 veikleikar** gerðu árásir eins og WannaCry og NotPetya kleift
- **Skjalafjölvi** eru áfram aðal afhendingaraðferð spilliforrita
- **USB-byggðar árásir** halda áfram að miða á loftþétta net
- **PowerShell misnotkun** hefur aukist verulega á síðustu árum

## 🛡️ Ghost Öryggisföll

Ghost veitir **16 Windows harðnunarföll** auk **Azure öryggissamþættingar**:

### Windows Endapunktsharðnun

| Fall | Tilgangur | Atriði til skoðunar |
|----------|---------|----------------|
| `Set-RDP` | Stjórnar fjartengingu skjáborðs | Getur haft áhrif á fjarsýningu |
| `Set-SMBv1` | Stjórnar eldri SMB samskiptareglum | Nauðsynleg fyrir mjög gömul kerfi |
| `Set-AutoRun` | Stjórnar AutoPlay/AutoRun | Getur haft áhrif á notendaþægindi |
| `Set-USBStorage` | Takmarkar USB geymslueiningar | Getur haft áhrif á lögmæta USB notkun |
| `Set-Macros` | Stjórnar Office fjölvikeyringu | Getur haft áhrif á fjölvivirk skjöl |
| `Set-PSRemoting` | Stjórnar PowerShell fjartengingu | Getur haft áhrif á fjarsýningu |
| `Set-WinRM` | Stjórnar Windows Remote Management | Getur haft áhrif á fjarsýningu |
| `Set-LLMNR` | Stjórnar nafnleysarsamskiptareglum | Venjulega öruggt að slökkva á |
| `Set-NetBIOS` | Stjórnar NetBIOS yfir TCP/IP | Getur haft áhrif á eldri forrit |
| `Set-AdminShares` | Stjórnar stjórnunarhlutdeild | Getur haft áhrif á fjarsækju skráa |
| `Set-Telemetry` | Stjórnar gagnasöfnun | Getur haft áhrif á greiningargetu |
| `Set-GuestAccount` | Stjórnar gestareikningi | Venjulega öruggt að slökkva á |
| `Set-ICMP` | Stjórnar ping svörum | Getur haft áhrif á netgreiningu |
| `Set-RemoteAssistance` | Stjórnar fjarhjálp | Getur haft áhrif á hjálparborðsrekstur |
| `Set-NetworkDiscovery` | Stjórnar netuppgötvun | Getur haft áhrif á netskoðun |
| `Set-Firewall` | Stjórnar Windows eldvegg | Mikilvægt fyrir netöryggi |

### Azure Skýjaöryggi

| Fall | Tilgangur | Kröfur |
|----------|---------|--------------|
| `Set-AzureSecurityDefaults` | Virkjar grunn Azure AD öryggi | Microsoft Graph heimildir |
| `Set-AzureConditionalAccess` | Stillir aðgangsstefnur | Azure AD P1/P2 leyfisveitingar |
| `Set-AzurePrivilegedUsers` | Endurskoðar forréttindareikningi | Altækir stjórnendaheimildir |

### Fyrirtækjauppsetningarvalkostir

| Aðferð | Notkunartilfelli | Kröfur |
|--------|----------|--------------|
| **Bein Keyrsla** | Prófanir, lítil umhverfi | Staðbundnar stjórnendaheimildir |
| **Group Policy** | Lénaumhverfi | Lénastjórnandi, GP stjórnun |
| **Microsoft Intune** | Skýjastýrð tæki | Intune leyfisveitingar, Graph API |

## 🚀 Fljótleg Byrjun

### Öryggismat
```powershell
# Hlaða Ghost einingu
IEX(Invoke-WebRequest 'https://raw.githubusercontent.com/jimrtyler/Ghost/main/Ghost.ps1')

# Athuga núverandi öryggisástand
Get-Ghost
```

### Grunnharðnun (Prófaðu Fyrst)
```powershell
# Nauðsynleg harðnun - prófaðu fyrst í tilraunaumhverfi
Set-Ghost -SMBv1 -AutoRun -Macros

# Fara yfir breytingar
Get-Ghost
```

### Fyrirtækjauppsetning
```powershell
# Group Policy uppsetning (lénaumhverfi)
Set-Ghost -SMBv1 -AutoRun -GroupPolicy

# Intune uppsetning (skýjastýrð tæki)
Set-Ghost -SMBv1 -RDP -USBStorage -Intune
```

## 📋 Uppsetningaraðferðir

### Valkostur 1: Bein Niðurhal (Prófanir)
```powershell
IEX(Invoke-WebRequest 'https://raw.githubusercontent.com/jimrtyler/Ghost/main/Ghost.ps1')
```

### Valkostur 2: Einingauppsetning
```powershell
# Setja upp úr PowerShell Gallery (þegar í boði)
Install-Module Ghost -Scope CurrentUser
Import-Module Ghost
```

### Valkostur 3: Fyrirtækjauppsetning
```powershell
# Afrita á netstaðsetningu fyrir Group Policy uppsetningu
# Stilla Intune PowerShell skrár fyrir skýjauppsetningu
```

## 💼 Notkunartilfelli Dæmi

### Lítil Fyrirtæki
```powershell
# Grunnvernd með lágmarksáhrifum
Set-Ghost -SMBv1 -AutoRun -Macros -ICMP
```

### Heilbrigðisumhverfi
```powershell
# HIPAA-miðuð harðnun
Set-Ghost -SMBv1 -RDP -USBStorage -AdminShares -Telemetry
```

### Fjármálaþjónusta
```powershell
# Háöryggis stillingarástand
Set-Ghost -RDP -SMBv1 -AutoRun -USBStorage -Macros -PSRemoting -AdminShares
```

### Skýja-Fyrsta Stofnun
```powershell
# Intune-stjórnuð uppsetning
Connect-IntuneGhost -Interactive
Set-Ghost -SMBv1 -RDP -AutoRun -Macros -Intune
```

## 🔍 Fallsuplýsingar

### Kjarna Harðnunarföll

#### Netþjónusta
- **RDP**: Lokar á fjartengda skjáborðsaðgang eða gerir port handahófskenndan
- **SMBv1**: Slekkur á eldri skráardeilingarsamskiptareglum
- **ICMP**: Kemur í veg fyrir ping svör fyrir könnun
- **LLMNR/NetBIOS**: Lokar á eldri nafnleysarsamskiptareglur

#### Forritaöryggi  
- **Fjölvi**: Slekkur á fjölvikeyringu í Office forritum
- **AutoRun**: Kemur í veg fyrir sjálfvirka keyrslu úr fjarlægjanlegu miðli

#### Fjarsýning
- **PSRemoting**: Slekkur á PowerShell fjarlotum
- **WinRM**: Stöðvar Windows Remote Management
- **Remote Assistance**: Lokar á fjarhjálpartengingar

#### Aðgangsstýring
- **Admin Shares**: Slekkur á C$, ADMIN$ hlutdeild
- **Guest Account**: Slekkur á gestareikningsaðgang
- **USB Storage**: Takmarkar USB tækjanotkun

### Azure Samþætting
```powershell
# Tengjast Azure leigjanda
Connect-AzureGhost -Interactive

# Virkja öryggissjálfgefnar stillingar
Set-AzureSecurityDefaults -Enable

# Stilla skilyrt aðgang
Set-AzureConditionalAccess -BlockLegacyAuth -RequireMFA

# Endurskoða forréttindanotendur
Set-AzurePrivilegedUsers -AuditOnly
```

### Intune Samþætting (Nýtt í v2)
```powershell
# Tengjast Intune
Connect-IntuneGhost -Interactive

# Setja upp í gegnum Intune stefnur
Set-IntuneGhost -Settings @{
    RDP = $true
    SMBv1 = $true
    USBStorage = $true
    Macros = $true
}
```

## ⚠️ Mikilvæg Atriði

### Prófunarkröfur
- **Tilraunaumhverfi**: Prófaðu allar stillingar fyrst í einangruðu umhverfi
- **Stigskipt Uppsetning**: Settu út smám saman til að greina vandamál
- **Endurheimtaráætlun**: Gakktu úr skugga um að þú getir snúið við breytingum ef þörf krefur
- **Skjölun**: Skráðu hvaða stillingar virka fyrir þitt umhverfi

### Möguleg Áhrif
- **Notendaframleiðni**: Sumar stillingar geta haft áhrif á daglegt vinnuflæði
- **Eldri Forrit**: Eldri kerfi geta þurft ákveðnar samskiptareglur
- **Fjaraðgangur**: Íhugaðu áhrif á lögmæta fjarsýningu
- **Viðskiptaferla**: Staðfestu að stillingar brjóti ekki mikilvægar aðgerðir

### Öryggistakmarkanir
- **Vörn í Dýpt**: Ghost er eitt lag öryggis, ekki heildarúrlausn
- **Stöðug Stjórnun**: Öryggi krefst stöðugs eftirlits og uppfærslna
- **Notendaþjálfun**: Tæknilegar stýringar verða að vera paraðar við öryggisvitund
- **Ógnirþróun**: Nýjar árásaraðferðir geta komist framhjá núverandi vörnum

## 🎯 Dæmi um Árásaraðstæður

Þó Ghost miði að algengum árásarvigrum fer sérstök forvörn eftir réttri útfærslu og prófun:

### WannaCry-stíl Árásir
- **Mildun**: `Set-Ghost -SMBv1` slekkur á viðkvæmum samskiptareglum
- **Íhugun**: Gakktu úr skugga um að engin eldri kerfi þurfi SMBv1

### RDP-byggð Lausnargjaldskera
- **Mildun**: `Set-Ghost -RDP` lokar á fjartengda skjáborðsaðgang
- **Íhugun**: Gæti þurft aðrar fjartengdaraðferðir

### Skjalabundin Spilliforrit
- **Mildun**: `Set-Ghost -Macros` slekkur á fjölvikeyringu
- **Íhugun**: Getur haft áhrif á lögmæt fjölvivirk skjöl

### USB-flutt Ógnanir
- **Mildun**: `Set-Ghost -USBStorage -AutoRun` takmarkar USB virkni
- **Íhugun**: Getur haft áhrif á lögmæta USB tækjanotkun

## 🏢 Fyrirtækjaeiginleikar

### Group Policy Stuðningur
```powershell
# Beita stillingum í gegnum Group Policy skrá
Set-Ghost -SMBv1 -RDP -AutoRun -GroupPolicy

# Stillingar gilda um allt lén eftir GP endurnýjun
gpupdate /force
```

### Microsoft Intune Samþætting
```powershell
# Búa til Intune stefnur fyrir Ghost stillingar
Set-IntuneGhost -Settings $GhostSettings -Interactive

# Stefnur setjast sjálfkrafa á stjórnuð tæki
```

### Reglufylgniskýrslur
```powershell
# Búa til öryggismatsskýrslu
Get-Ghost | Export-Csv -Path "SecurityAudit-$(Get-Date -Format 'yyyy-MM-dd').csv"

# Azure öryggisstaða skýrsla
Get-AzureGhost | Out-File "AzureSecurityReport.txt"
```

## 📚 Bestu Starfsvenjur

### Fyrir Uppsetningu
1. **Skjalfesta Núverandi Stöðu**: Keyrðu `Get-Ghost` áður en breytingar eru gerðar
2. **Rækilega Prófun**: Staðfestu í umhverfi sem ekki er framleiðsla
3. **Endurheimtaráætlun**: Vittu hvernig á að snúa við hverri stillingu
4. **Endurskoðun Hagsmunaaðila**: Gakktu úr skugga um að viðskiptaeiningar samþykki breytingar

### Meðan á Uppsetningu Stendur
1. **Stigskipt Nálgun**: Settu fyrst upp á tilraunahópa
2. **Fylgjast með Áhrifum**: Fylgstu með kvörtunum notenda eða kerfivandamálum
3. **Skjalfesta Vandamál**: Skráðu öll vandamál fyrir framtíðartilvísun
4. **Miðla Breytingum**: Láttu notendur vita af öryggisbótum

### Eftir Uppsetningu
1. **Reglulegt Mat**: Keyrðu `Get-Ghost` reglulega til að staðfesta stillingar
2. **Uppfæra Skjölun**: Haltu öryggisskilgreiningum uppfærðum
3. **Endurskoða Virkni**: Fylgstu með öryggisatvikum
4. **Stöðug Bæting**: Aðlagaðu stillingar byggt á ógnirlandslagi

## 🔧 Úrræðaleit

### Algeng Vandamál
- **Heimildavillur**: Gakktu úr skugga um að PowerShell lota sé aukin
- **Þjónustuháðir**: Sumar þjónustur geta haft háðir
- **Forritasamhæfi**: Prófaðu með viðskiptaforritum
- **Nettengingar**: Staðfestu að fjaraðgangur virki enn

### Endurheimtarvalkostir
```powershell
# Enduvirkja sérstakar þjónustur ef þörf krefur
Set-RDP -Enable
Set-SMBv1 -Enable
Set-AutoRun -Enable
Set-Macros -Enable
```

## 👨‍💻 Um Höfundinn

**Jim Tyler** - Microsoft MVP fyrir PowerShell
- **YouTube**: [@PowerShellEngineer](https://youtube.com/@PowerShellEngineer) (10.000+ áskrifendur)
- **Fréttabréf**: [PowerShell.News](https://powershell.news) - Vikulegar öryggisupplýsingar
- **Höfundur**: "PowerShell for Systems Engineers"
- **Reynsla**: Áratugir af PowerShell sjálfvirkni og Windows öryggi

## 📄 Leyfi og Fyrirvari

### MIT Leyfi
Ghost er veitt undir MIT leyfi fyrir frjálsa notkun, breytingu og dreifingu.

### Öryggisfyrirvari
- **Engin Ábyrgð**: Ghost er veitt "eins og er" án nokkurs konar ábyrgðar
- **Prófanir Nauðsynlegar**: Prófaðu alltaf fyrst í umhverfi sem ekki er framleiðsla
- **Fagleg Leiðsögn**: Hafðu samband við öryggissérfræðinga fyrir framleiðsluuppsetningar
- **Rekstraráhrif**: Höfundar eru ekki ábyrgir fyrir nokkrum rekstrarruflingum
- **Yfirgripsmikið Öryggi**: Ghost er einn hluti af fullkominni öryggisstefnu

### Stuðningur
- **GitHub Issues**: [Tilkynna villur eða biðja um eiginleika](https://github.com/jimrtyler/Ghost/issues)
- **Skjölun**: Notaðu `Get-Help <function> -Full` fyrir ítarlega hjálp
- **Samfélag**: PowerShell og öryggissamfélagsspjallborð

---

**🔒 Styrktu öryggisástand þitt með Ghost - en prófaðu alltaf fyrst.**

```powershell
# Byrjaðu með mati, ekki forsendum
Get-Ghost
```

**⭐ Stjörnumerktu þetta geymsla ef Ghost hjálpar til við að bæta öryggisástand þitt!**