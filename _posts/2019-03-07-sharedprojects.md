---
layout: post
published: true
title: Deling af fælleskode - Shared Projects
---
Når man laver applikationer med Xamarin.forms. Håndtere man de platformspecifikke ting i et project for sig selv fx Xamarin.Driod for Andriod. Man har så mulighed for at dele bla logik der er fælles på tværs af platformene via et 3. project. Ikke al kode er (desværre) mulig at dele imellem platforme og der vil være imellem 14 og 30 % platformspecifik kode man er nød til at skrive. For at kode er mulig at dele på tværs af platformene er den altså nødsaget til at være uafhængig af platformspecifikke Api'er.

Noget af det man skal tænke over når man laver cross platform developement er hvad jeg skal jeg dele imellem platformene(projekterne) og hvad skal jeg holde på de specifike platforme. En god hovedregel at tænke hvis man gentager noget på tværs af platformene skal man overveje om man kan skrive det/implementere det på en måde så at man kan dele det på tværs af platformene. Og omvendt hvis man skriver noget som er meget platformspecifikt( fx api'er der kun virker på den gældende platform fx Uikit for IOS) i det delte projekt skal man nok overveje om det ikke skal holdes på projektet så man kan bruge platformspecifikt kode. 
 
Ideen med dele(sharing) mellem projekter er at dele logikken og data structurer med Xamarin.forms er ideen også at man deler UI Design. Man kan dele på flere måder. Her er de måder jeg har prøvet indtil videre:De måder jeg har prøvet kan deles op i to kategorier: Shared projects og shared Compiled Binaries. Ganske kort er forskellen at man i shared projects dele man kodefilerne ved at samle dem i collections som bliver consumed af de platformspecifikke projecter og compilet direkte til ens app. Man kan altså dele indhold inden for ens solution.
Når man laver en reference til et shared project bliver det håndteret som at alt indholdet i shared projected er addet direkte til det andet projekt når det bliver compilet.  
Her er fra et projekt jeg har arbejdet med hvor man kan se der er et projekt for hver platform og et shared project(MyTunes.Shared)

![Mytunes.PNG]({{site.baseurl}}/img/Mytunes.PNG)

Man kan dele koden på 3 forskellige måder med shared projects, Conditional Compilation, class mirroring & Partial Class+methods. Jeg vil ikke gå i dybden med dem her men ganske kort er conditional compilation hvor man complileren udfører forskellig kode afhængig af parametre givet under complingen. Jeg kommer muligvis til at gå mere i dybden med det her i kommende indlæg. Jeg har brugt Conditional Compilation i mit project som kan ses her: 

```csharp

private static Stream OpenData()
		{
#if __ANDROID__
            return Android.App.Application.Context.Assets.Open(Filename);
#elif  __IOS__
            
            
            return File.OpenRead(Filename);

#else

            return null;
#endif
        }

```

Hvor de forskellige if-directiver afgør hvilken kode der skal executes. I det her tilfælde var det hvordan man åbnede en fil. Her kan man se den forskellige måde IOS og Android håndtere den funktion på. Shared projects er nemme at arbejde med, når det er mindre projekter hvor man har alle projektor i samme solution. For man er nødsaget til at have adgang til sourcekoden for at bearbejde den og det er ulempen ved at bruge det. Jeg vil senere sammenligne det med shared binaries og mine erfaringer med begge måder at gøre det på. 


