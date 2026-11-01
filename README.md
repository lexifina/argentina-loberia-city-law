# Lobería: municipal law history in git

The municipal law of the Partido de Lobería (Province of Buenos Aires), Argentina, as a git history: one file per article, one commit per ordinance on the day it took effect. `git log` lists the changes; checking out a date gives the text the record holds for that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `ar-b-loberia/`. The province's law is in [lexifina/argentina-buenos-aires-law](https://github.com/lexifina/argentina-buenos-aires-law) and Argentina's national law in [lexifina/argentina-law](https://github.com/lexifina/argentina-law).

The text is in Spanish, exactly as the source prints it.

## What this repository holds

6 ordinances so far, in force from 7 October 2017 to 4 January 2026, each as published in the Boletín Oficial Municipal de Lobería, added in parts.

| Folder | Ordinance | History |
| --- | --- | --- |
| `ordenanza-2129-2017/` | Ordenanza 2129/2017: AUTORIZASE al Departamento Ejecutivo Municipal a ACEPTAR la única propuesta considerada oferta por reunir los requisitos exigidos según la … | in force 7 October 2017 |
| `ordenanza-2131-2017/` | Ordenanza 2131/2017: EL Honorable Concejo Deliberante de Lobería DECLARA de INTERÉS MUNICIPAL, a los efectos de su financiación por medio del Fondo Municipal de… | in force 7 October 2017 |
| `ordenanza-2138-2017/` | Ordenanza 2138/2017: CRÉASE en el ámbito del Partido de LOBERIA el FONASAL “FONDO DE ASISTENCIA EN SALUD”.- | in force 15 October 2017 |
| `ordenanza-2359-2019/` | Ordenanza 2359/2019: ADHIÉRASE el Municipio de Lobería a la Ley Provincial Nº 15.134 de CAPACITACIÓN OBLIGATORIA EN LA TEMÁTICA DE GÉNERO Y VIOLENCIA CONTRA LAS… | in force 6 October 2019 |
| `ordenanza-2716-2022/` | Ordenanza 2716/2022: EL Honorable Concejo Deliberante de Lobería DECLARA de INTERÉS MUNICIPAL, a los efectos de su financiación por medio del Programa Municipal… | in force 25 December 2022 |
| `ordenanza-3030-2025/` | Ordenanza 3030/2025: APRUÉBASE la ORDENANZA FISCAL para el año 2026 que como ANEXO I forma parte de la presente. | in force 4 January 2026 |

## Source

Sistema de Boletines Oficiales Municipales (SIBOM), Subsecretaría Legal y Técnica, Secretaría General, Provincia de Buenos Aires: Boletín Oficial Municipal de Lobería, <https://sibom.slyt.gba.gob.ar/cities/73>. SIBOM is the platform on which each municipality of the Province of Buenos Aires makes its Boletín Oficial Municipal (Ley 14.491). For each bulletin it lists the ordinances it published; each ordinance has its own page with the text as published (HTML). The site states no terms restricting reuse.

## Dates

- Each commit is dated at **noon, America/Argentina/Buenos_Aires, on the day the ordinance took effect**: the day its own vigencia clause names, or otherwise the ninth day after its publication in the Boletín Oficial Municipal de Lobería (Código Civil y Comercial de la Nación, arts. 5 and 6).
- Each ordinance is its text as published. Later ordinances that amend it are separate folders; their changes are not merged into the earlier text.
- Versions that take effect after the retrieval day are on the `futuro` branch, never merged into `main`.

## Files

`<ordinance>/art-005.md` is Artículo 5; `encabezado.md` holds the number, the place and date, the expediente line and anything printed before Artículo 1. Signatures and annexes stay in the file of the article they follow. One paragraph per line.

## How it is checked

- Every version of every ordinance is read back from git on the day it took effect and on the day before (`tools/check_repo.py`); both must match `corpus.json`.
- The letters and digits of every version equal those of the source page it was read from (read again with an independent HTML reader), so no word is lost or added.
- Health checks: no merge commits, commit dates never go backwards, nothing dated in the future, and every commit's trailers parse.

## Limits

This is not an official publication. The binding text is the one published in the Boletín Oficial Municipal de Lobería. Only the ordinances listed above are included, and amendments are not consolidated into the texts they amend.

## Left out

197 ordinances that SIBOM lists in the period covered are not included, because the Boletín Oficial Municipal de Lobería page gives no article text to read:

| Ordinance | Published | Why | Page |
| --- | --- | --- | --- |
| Ordenanza 2074-17 | 22 March 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/56/contents/1004941> |
| Ordenanza 2076-17 | 22 March 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/56/contents/1004962> |
| Ordenanza 2081-17 | 22 March 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/56/contents/1009351> |
| Ordenanza 2082-17 | 22 March 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/56/contents/1009355> |
| Ordenanza 2089-17 | 15 May 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/121/contents/1137164> |
| Ordenanza 2101-17 | 15 May 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/121/contents/1137237> |
| Ordenanza 2105-17 | 14 June 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/154/contents/1140212> |
| Ordenanza 2113-17 | 27 July 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/229/contents/1147357> |
| Ordenanza 2116-17 | 27 July 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/229/contents/1147440> |
| Ordenanza 2118-17 | 27 July 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/229/contents/1147458> |
| Ordenanza 2119-17 | 27 July 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/229/contents/1147466> |
| Ordenanza 2147-17 | 13 December 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/526/contents/1173311> |
| Ordenanza 2148-17 | 13 December 2017 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/526/contents/1173314> |
| Ordenanza 2157-17 | 23 January 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/641/contents/1183333> |
| Ordenanza 2179-18 | 23 May 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/928/contents/1211036> |
| Ordenanza 2190-18 | 23 May 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/928/contents/1211537> |
| Ordenanza 2191-18 | 23 May 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/928/contents/1211555> |
| Ordenanza 2195-18 | 21 June 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1016/contents/1215991> |
| Ordenanza 2211-18 | 6 August 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1159/contents/1229176> |
| Ordenanza 2219-18 | 6 August 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1159/contents/1229281> |
| Ordenanza 2224-18 | 5 September 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1297/contents/1239627> |
| Ordenanza 2231-18 | 5 September 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1297/contents/1240479> |
| Ordenanza 2232-18 | 5 September 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1297/contents/1240485> |
| Ordenanza 2236-18 | 21 September 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1319/contents/1243831> |
| Ordenanza 2239-18 | 21 September 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1319/contents/1243917> |
| Ordenanza 2240-18 | 21 September 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1319/contents/1243926> |
| Ordenanza 2245-18 | 21 September 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1319/contents/1244703> |
| Ordenanza 2246-18 | 21 September 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1319/contents/1244705> |
| Ordenanza 2247-18 | 21 September 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1319/contents/1244882> |
| Ordenanza 2251-18 | 11 October 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1390/contents/1253079> |
| Ordenanza 2252-18 | 11 October 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1390/contents/1253157> |
| Ordenanza 2254-18 | 11 October 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1390/contents/1253174> |
| Ordenanza 2256-18 | 11 October 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1390/contents/1253180> |
| Ordenanza 2257-18 | 11 October 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1390/contents/1253185> |
| Ordenanza 2266-18 | 7 November 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1546/contents/1261395> |
| Ordenanza 2267-18 | 7 November 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1546/contents/1261414> |
| Ordenanza 2270-18 | 7 November 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1546/contents/1261429> |
| Ordenanza 2275-18 | 7 December 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1611/contents/1271101> |
| Ordenanza 2278-18 | 7 December 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1611/contents/1271124> |
| Ordenanza 2280-18 | 7 December 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1611/contents/1271159> |
| Ordenanza 2282-18 | 7 December 2018 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1611/contents/1271511> |
| Ordenanza 2294-19 | 20 March 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1940/contents/1302405> |
| Ordenanza 2297-19 | 20 March 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/1940/contents/1302464> |
| Ordenanza 2303-19 | 23 April 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2102/contents/1317258> |
| Ordenanza 2307-19 | 23 April 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2102/contents/1317370> |
| Ordenanza 2310-19 | 31 May 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2276/contents/1332652> |
| Ordenanza 2312-19 | 31 May 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2276/contents/1332655> |
| Ordenanza 2318-19 | 31 May 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2276/contents/1332666> |
| Ordenanza 2321-19 | 24 June 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2404/contents/1341402> |
| Ordenanza 2326-19 | 24 June 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2404/contents/1342167> |
| Ordenanza 2329-19 | 24 June 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2404/contents/1342171> |
| Ordenanza 2333-19 | 24 June 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2404/contents/1342191> |
| Ordenanza 2340-19 | 18 July 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2418/contents/1350666> |
| Ordenanza 2341-19 | 18 July 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/2418/contents/1350714> |
| Ordenanza 2367-19 | 10 December 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3004/contents/1407493> |
| Ordenanza 2368-19 | 10 December 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3004/contents/1407508> |
| Ordenanza 2372-19 | 10 December 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3004/contents/1407564> |
| Ordenanza 2373-19 | 10 December 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3004/contents/1407569> |
| Ordenanza 2374-19 | 10 December 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3004/contents/1407574> |
| Ordenanza 2375-19 | 10 December 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3004/contents/1407602> |
| Ordenanza 2378-19 | 10 December 2019 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3004/contents/1407623> |
| Ordenanza 2382-19 | 7 January 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3006/contents/1416387> |
| Ordenanza 2383-19 | 7 January 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3006/contents/1416405> |
| Ordenanza 2392-20 | 3 June 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3725/contents/1456723> |
| Ordenanza 2394-20 | 3 June 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3725/contents/1456766> |
| Ordenanza 2396-20 | 3 June 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3725/contents/1456834> |
| Ordenanza 2400-20 | 3 June 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3725/contents/1456951> |
| Ordenanza 2411-20 | 28 July 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3927/contents/1471975> |
| Ordenanza 2412-20 | 28 July 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3927/contents/1471978> |
| Ordenanza 2414-20 | 28 July 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/3927/contents/1471984> |
| Ordenanza 2423-20 | 25 August 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/4116/contents/1481286> |
| Ordenanza 2425-20 | 25 August 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/4116/contents/1481293> |
| Ordenanza 2430-20 | 25 August 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/4116/contents/1481307> |
| Ordenanza 2431-20 | 25 August 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/4116/contents/1481309> |
| Ordenanza 2437-20 | 16 October 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/4373/contents/1498198> |
| Ordenanza 2444-20 | 3 November 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/4453/contents/1504274> |
| Ordenanza 2445-20 | 20 November 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/4527/contents/1509281> |
| Ordenanza 2457-20 | 3 December 2020 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/4581/contents/1513169> |
| Ordenanza 2475-21 | 22 March 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5033/contents/1555111> |
| Ordenanza 2491-21 | 22 March 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5033/contents/1555143> |
| Ordenanza 2492-21 | 22 March 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5033/contents/1555145> |
| Ordenanza 2493-21 | 22 March 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5033/contents/1555147> |
| Ordenanza 2499-21 | 15 April 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5179/contents/1562281> |
| Ordenanza 2502-21 | 15 April 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5179/contents/1562323> |
| Ordenanza 2504-21 | 15 April 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5179/contents/1562379> |
| Ordenanza 2518-21 | 8 June 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5423/contents/1582464> |
| Ordenanza 2522-21 | 16 June 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5526/contents/1586065> |
| Ordenanza 2526-21 | 16 June 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5526/contents/1586127> |
| Ordenanza 2542-21 | 15 July 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/5618/contents/1595794> |
| Ordenanza 2550-21 | 20 October 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6030/contents/1631947> |
| Ordenanza 2553-21 | 20 October 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6030/contents/1632001> |
| Ordenanza 2566-21 | 3 December 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6256/contents/1652399> |
| Ordenanza 2568-21 | 3 December 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6256/contents/1652381> |
| Ordenanza 2569-21 | 3 December 2021 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6256/contents/1652614> |
| Ordenanza 2579-21 | 3 January 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6374/contents/1664086> |
| Ordenanza 2586-22 | 8 April 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6788/contents/1702366> |
| Ordenanza 2594-22 | 8 April 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6788/contents/1703493> |
| Ordenanza 2595-22 | 8 April 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6788/contents/1703499> |
| Ordenanza 2596-22 | 8 April 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6788/contents/1703505> |
| Ordenanza 2601-22 | 8 April 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6788/contents/1703561> |
| Ordenanza 2604-22 | 8 April 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6788/contents/1703624> |
| Ordenanza 2610-20 | 8 April 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6788/contents/1703760> |
| Ordenanza 2612-22 | 8 April 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6788/contents/1703796> |
| Ordenanza 2613-22 | 13 April 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6865/contents/1705194> |
| Ordenanza 2633-22 | 12 May 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/6957/contents/1716138> |
| Ordenanza 2643-22 | 1 June 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7094/contents/1725000> |
| Ordenanza 2645-22 | 5 July 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7199/contents/1740063> |
| Ordenanza 2653-22 | 5 July 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7199/contents/1740085> |
| Ordenanza 2654-22 | 5 July 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7199/contents/1740087> |
| Ordenanza 2656-22 | 5 July 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7199/contents/1740091> |
| Ordenanza 2657-22 | 5 July 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7199/contents/1740093> |
| Ordenanza 2671-22 | 6 September 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7460/contents/1767685> |
| Ordenanza 2674-22 | 6 September 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7460/contents/1767695> |
| Ordenanza 2678-22 | 14 October 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7651/contents/1785889> |
| Ordenanza 2681-22 | 14 October 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7651/contents/1785931> |
| Ordenanza 2682-22 | 14 October 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7651/contents/1785938> |
| Ordenanza 2694-22 | 16 November 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7762/contents/1798241> |
| Ordenanza 2696-22 | 16 November 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7762/contents/1798306> |
| Ordenanza 2698-22 | 16 November 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/7762/contents/1798322> |
| Ordenanza 2720-22 | 28 December 2022 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/8003/contents/1819256> |
| Ordenanza 2723-23 | 24 January 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/8184/contents/1832149> |
| Ordenanza 2728-23 | 19 April 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/8459/contents/1866768> |
| Ordenanza 2734-23 | 19 April 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/8459/contents/1866790> |
| Ordenanza 2740-23 | 19 April 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/8459/contents/1867002> |
| Ordenanza 2742-23 | 19 April 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/8459/contents/1867174> |
| Ordenanza 2750-23 | 9 May 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/8695/contents/1878317> |
| Ordenanza 2767-23 | 14 July 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9004/contents/1912484> |
| Ordenanza 2768-23 | 14 July 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9004/contents/1912486> |
| Ordenanza 2770-23 | 14 July 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9004/contents/1912498> |
| Ordenanza 2774-234 | 14 July 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9004/contents/1912571> |
| Ordenanza 2775-23 | 14 July 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9004/contents/1912575> |
| Ordenanza 2781-23 | 14 July 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9004/contents/1912594> |
| Ordenanza 2793-23 | 14 September 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9389/contents/1944658> |
| Ordenanza 2801-23 | 7 December 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9843/contents/1991199> |
| Ordenanza 2805-23 | 7 December 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9843/contents/1991359> |
| Ordenanza 2806-23 | 7 December 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9843/contents/1991400> |
| Ordenanza 2807-23 | 7 December 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9843/contents/1991419> |
| Ordenanza 2808-23 | 7 December 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9843/contents/1991439> |
| Ordenanza 2815-23 | 7 December 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9843/contents/1991584> |
| Ordenanza 2818-23 | 11 December 2023 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9865/contents/1992206> |
| Ordenanza 2824-23 | 4 January 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/9998/contents/2002564> |
| Ordenanza 2831-24 | 7 April 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10398/contents/2035013> |
| Ordenanza 2832-24 | 7 April 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10398/contents/2035015> |
| Ordenanza 2836-24 | 7 April 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10398/contents/2035023> |
| Ordenanza 2837-24 | 7 April 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10398/contents/2035025> |
| Ordenanza 2841-24 | 7 April 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10398/contents/2035033> |
| Ordenanza 2852-24 | 2 May 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10508/contents/2047800> |
| Ordenanza 2861-24 | 6 July 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10841/contents/2074754> |
| Ordenanza 2863-24 | 6 July 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10841/contents/2074776> |
| Ordenanza 2869-24 | 6 July 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10841/contents/2076079> |
| Ordenanza 2873-24 | 6 July 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10841/contents/2076087> |
| Ordenanza 2884-24 | 6 July 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10841/contents/2076152> |
| Ordenanza 2887-24 | 6 July 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/10841/contents/2076158> |
| Ordenanza 2898-24 | 22 July 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/11009/contents/2083245> |
| Ordenanza 2901-24 | 6 August 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/11094/contents/2089453> |
| Ordenanza 2905-24 | 26 August 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/11212/contents/2098085> |
| Ordenanza 2908-24 | 26 August 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/11212/contents/2098101> |
| Ordenanza 2915-24 | 1 October 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/11448/contents/2117775> |
| Ordenanza 2916-24 | 1 October 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/11448/contents/2117793> |
| Ordenanza 2926-24 | 23 October 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/11565/contents/2125771> |
| Ordenanza 2933-24 | 6 December 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/11739/contents/2143368> |
| Ordenanza 2934-24 | 6 December 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/11739/contents/2143425> |
| Ordenanza 2946-24 | 6 December 2024 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/11739/contents/2144203> |
| Ordenanza 2961-25 | 16 April 2025 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/12487/contents/2202701> |
| Ordenanza 2977-25 | 16 April 2025 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/12487/contents/2203354> |
| Ordenanza 2978-25 | 16 April 2025 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/12487/contents/2203372> |
| Ordenanza 2983-25 | 13 May 2025 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/12764/contents/2216297> |
| Ordenanza 2990-25 | 3 June 2025 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/12832/contents/2228888> |
| Ordenanza 2994-25 | 3 June 2025 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/12832/contents/2229139> |
| Ordenanza 3005-25 | 30 September 2025 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/13553/contents/2288468> |
| Ordenanza 3006-25 | 30 September 2025 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/13553/contents/2288475> |
| Ordenanza 3011-25 | 30 September 2025 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/13553/contents/2288580> |
| Ordenanza 3034-25 | 2 January 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/14167/contents/2331157> |
| Ordenanza 3044-26 | 12 January 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/14220/contents/2334846> |
| Ordenanza 3049-26 | 21 April 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/14753/contents/2377472> |
| Ordenanza 3055-26 | 21 April 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/14753/contents/2377661> |
| Ordenanza 3057-26 | 21 April 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/14753/contents/2377710> |
| Ordenanza 3063-26 | 21 April 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/14753/contents/2377861> |
| Ordenanza 3065-26 | 21 April 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/14753/contents/2377909> |
| Ordenanza 3066-26 | 21 April 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/14753/contents/2377935> |
| Ordenanza 3068-26 | 27 May 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15069/contents/2395870> |
| Ordenanza 3072-26 | 27 May 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15069/contents/2395899> |
| Ordenanza 3073-26 | 27 May 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15069/contents/2395914> |
| Ordenanza 3074-26 | 27 May 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15069/contents/2395925> |
| Ordenanza 3070-26 | 18 June 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15093/contents/2396540> |
| Ordenanza 3078-26 | 18 June 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15093/contents/2405823> |
| Ordenanza 3079-26 | 18 June 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15093/contents/2405834> |
| Ordenanza 3081-26 | 18 June 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15093/contents/2405854> |
| Ordenanza 3082-26 | 19 August 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15513/contents/2432174> |
| Ordenanza 3083-26 | 19 August 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15513/contents/2431597> |
| Ordenanza 3089-26 | 19 August 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15513/contents/2431970> |
| Ordenanza 3091-26 | 19 August 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15513/contents/2432068> |
| Ordenanza 3092-26 | 19 August 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15513/contents/2432115> |
| Ordenanza 3093-26 | 19 August 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15513/contents/2432125> |
| Ordenanza 3095-26 | 15 September 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15710/contents/2444692> |
| Ordenanza 3101-26 | 15 September 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15710/contents/2444791> |
| Ordenanza 3113-26 | 23 October 2026 | number or publication date not readable | <https://sibom.slyt.gba.gob.ar/bulletins/15962/contents/2464277> |
