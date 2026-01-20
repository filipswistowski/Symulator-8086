# Symulator MOV/XCHG dla 8086 — Filip Świstowski	

## Cel projektu
Celem projektu jest wykonanie prostego symulatora wybranych rozkazów procesora 8086: MOV i XCHG dla rejestrów AX, BX, CX, DX oraz MOV dla transferu pamięć↔rejestr.

## Procesor i rejestry
Projekt nawiązuje do architektury 8086 i wykorzystuje 16‑bitowe rejestry ogólnego przeznaczenia (AX, BX, CX, DX) oraz rejestry używane w adresowaniu (BX, BP, SI, DI).

## Symulowane rozkazy
- MOV: kopiuje operand źródłowy do docelowego (bez zamiany wartości).
- XCHG: zamienia zawartości dwóch operandów.

Symulator obsługuje:
- MOV rejestr↔rejestr (AX/BX/CX/DX)
- XCHG rejestr↔rejestr (AX/BX/CX/DX)
- MOV pamięć↔rejestr (AX/BX/CX/DX), zapis/odczyt słowa (16-bit) w pamięci bajtowej (little-endian)

## Tryby adresowania (wyliczanie adresu)
Symulator wylicza adres efektywny EA jako sumę elementów: base + index + offset (displacement).
Zastosowane tryby:
- bazowe: BX lub BP + offset
- indeksowe: SI lub DI + offset
- indeksowo‑bazowe: (BX lub BP) + (SI lub DI) + offset

## Interfejs i walidacja
- Wszystkie pola wejściowe akceptują wartości w kodzie szesnastkowym.
- Rejestry są ograniczone do 16 bitów (0000–FFFF).
- Pamięć ma rozmiar 64KB i jest adresowana bajtowo; zapis słowa zajmuje 2 kolejne bajty.

## Instrukcja uruchomienia
1. Otworzyć plik `symulator_8086_Świstowski.html` w przeglądarce.
2. Wpisać wartości rejestrów i offset (hex).
3. Wybrać tryb adresowania i wykonać MOV/XCHG.
