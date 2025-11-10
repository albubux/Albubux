

# Albubux (BUBX)

**Łańcuch:** Inteligentny łańcuszek BNB (BEP-20)  
**Umowa:** `0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9`  
**Nazwa / Symbol / Miejsca dziesiętne:** Albubux / BUBX / 9  
**Całkowita podaż:** zobacz BscScan „Przeczytaj umowę”

Albubux to prowadzony przez społeczność LiquidityGeneratorToken z refleksjami posiadaczy, automatyczną płynnością (LP → `0xmartwy`) oraz opcjonalną opłatę na rzecz organizacji charytatywnej (musi wynosić 0, jeśli adres organizacji charytatywnej to `0x0`).  
Przedsprzedaż: **0%** opłaty. Cel polityki po umieszczeniu na liście: **~1% ogółem**, z **limit polityki publicznej ≤ 5%**.  
*(Inteligentna umowa wymusza sztywny limit **≤ 25%** wszystkich opłat.)*

## Spinki do mankietów
- **Oficjalna księga:** .https://github.com/albubux/Albubux/blob/main/whitepaper/Albubux_Whitepaper.md
- **Inwestor, plik README:** ./whitepaper/Albubux_README.md
- **BscScan (umowa):** 0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9
- **Rewizja** https://blocksafu.com/certificate/0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9
- **Wyprzedaż Dx** https://www.dx.app/dxsale/view?address=0x3aea24db9214663b4d40E8f2557Fc3B5bF96cBbb&chain=BSC
- **Strona internetowa / portale społecznościowe:** https://albubux.com

## Najważniejsze informacje o kontrakcie
- Pojedynczy, jednolity harmonogram opłat za transfer (bez oddzielnego kodu kupna/sprzedaży).
- Opłaty (punkty bazowe powyżej 10 000): `_opłata podatkowa` (odbicia), `_opłata za płynność` (automatyczny LP), `_opłata charytatywna` (Do `_adres organizacji charytatywnej`).
- **Twarda czapka:** `_podatek + _liq + _dobroczynność ≤ 25%` (konstruktor + ustawiacze).
- **Zamień i upłynnij próg:** domyślnie ~0,1% podaży; właściciel może ustawić ale **≥ 0,05%**.
- Narzędzia właściciela: `ustaw*Procent opłaty`, `setSwapBackSettings`, `wyklucz z opłaty`, `wyklucz z nagrody/włącz w nagrodzie`, `przeniesienie własności`, `zrzec się własności`.

## Sprawdź/Twórz notatki
- **Kompilator:** Solidność `0.8.4` (dokładny), **Optymalizacja 200 uruchomień**.  
- Jeśli BscScan pokazuje „Podobne dopasowanie”, jest to oczekiwane w przypadku tego szablonu.
- Tokeny LP są wysyłane do `0xmartwy` na mocy umowy o dodaniu płynności.
