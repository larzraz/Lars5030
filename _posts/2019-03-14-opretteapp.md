---
layout: post
published: true
title: At oprette en app
---

Målet med at lave apps i xamarin.forms er at give oprette applikationer der kan køre cross-platform. Og altså eliminere behovet for at lave to(eller flere afhængig af ønskede platforme) applikationer, der er platformspecifikke. Man slipper for at gentage en masse kode. Du slipper ikke helt uden om at lave ting der er specifikt for en platform, nogle ting er kun supported af den ene platform. Eller skal håndteres på en specifik måde. Men langt hen af vejen skriver du koden i dit delte project. Og så i dine platformspecifikke projekter håndtere det platform specifikke kode.

En App skal have et user interface for at præsentere noget. Hvordan man kan designe sine views/hvilke layouts der findes, kommer i et andet opslag. Men tankerne her er at fortælle lidt om måderne man kan implementere sine views på. Og mine erfaringer med dem. 

Ganske kort. Når man vil præsentere sit indhold i appen har man forskellige muligheder. Dem jeg har brugt mest er contentpage. Og Tabbedpage. De har nogle features som gør dem foretrukne. I hvert fald for mig. Jeg kommer ind på i et andet opslag. Men lad os tage udgangspunkt i contentpage. Som er en page til at fremvise content. Man kan designe sin page som enten C#-kode eller XAML kode. Fordelen ved ren kode var for mig at syntaxen er c# og dermed allerede noget jeg har arbejdet med og nemmere at forholde sig til i starten. Visual studio supportere intellisense for c# som er rart når man kode, og især ny og gerne vil lege lidt med det. Det virker mere overskueligt at gennemse koden. Og så er det bare nemmere at finde hjælp på nettet hvis man har behov for det. 

Men jeg er alligevel større fan af at bruge XAML. XAML er et XML-baseret markup sprog. XAML i Xamarin, minder utroligt meget om XAML i WPF, som jeg tidligere på uddannelsen har leget med. Derfor var det ikke helt nyt, men alligevel var der noget knas en gang imellem. Jeg fortrækker XAML fordi det giver bedre separation of concern. Og overordnet en klarere og mere overskueligt arkitektur. Og når man først er blevet vandt til at bruge XAML. Så fungere det rigtig godt. Og selvom C#-koden er nemmere at gennemskue. Syntes jeg det er langt nemmere at bygge dine views op i XAML. I WPF-applikationer kan man point and clicke de forskellige elementer man ønsker ind på sine views. Det var jeg stor fan af dengang. Men eftersom dette ikke er en mulighed i Xamarin, er man i nød til at bruge layouts og skrive alt koden selv. Det er jeg blevet større fan af nu. Da det bare giver et mere præcist view og i øvrigt sørger for at din applikation fungere uanset retningen af skærmen(altså om den er stående eller liggene). Største minus i XAML er nok er det er sværere at finde hjælp på nettet end c#.Så alt i alt fungere begge muligheder fint. Men XAML er for mig smartere pga arktitektur. Og det jeg har valgt at bruge fremover til mine applikationer.




