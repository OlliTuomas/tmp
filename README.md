# AppLogger

Tässä projektissa luodaan kaksi erillistä .NET-projektia:
1. **AppLogger**: Luokkakirjasto (class library), joka tarjoaa lokipalvelun `Logger.Log`.
2. **App**: Konsolisovellus, joka hyödyntää `AppLogger`-kirjastoa ja käyttää sen `Logger`-luokkaa.

## Käyttöönotto

### 1. Ratkaisun ja projektien luominen

Avaa PowerShell ja suorita seuraavat komennot:

```powershell
# Siirry hakemistoon ja luo uusi kansio projektille
cd C:\Temp
mkdir Tehtava4
cd Tehtava4

# Luo ratkaisutiedosto (sln)
dotnet new sln

# Luo AppLogger classlib-projekti
dotnet new classlib -n AppLogger

# Luo App console-projekti
dotnet new console -n App

# Lisää molemmat projektit ratkaisuun
dotnet sln .\Tehtava4.sln add .\AppLogger\AppLogger.csproj .\App\App.csproj

# Lisää viittaus AppLogger-projektiin App-projektista
dotnet add .\App\App.csproj reference .\AppLogger\AppLogger.csproj