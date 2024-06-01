---
title: Handige tempo- en snelheidcalculator
authors:
  - marijn-kok
date: 2024-05-16T23:37:48+02:00
featuredImage: /images/pexels-mateusz-dach-99805-332835.jpg
categories: []
tags: []
enableMath: true
summary: Bereken je tempo met afstand en tijd, converteer km/h naar tempo en vice-versa.
---
Sinds een tijdje zit ik te trainen voor een marathon. Bij hardlopen word gebruikgemaakt van de eenheid "minuten per kilometer" in plaats van kilometer per uur. Dit heet tempo, of *pace* in het Engels. Ik heb echter nog steeds geen gevoel voor hoe snel het tempo "5" is. Online tools om tempo en km/h om te zetten bleken slecht, dus ~~maakte ik mijn eigen~~ gebruikte ik ChatGPT om deze tool te genereren. Ik heb hem daarna wel aangepast naar mijn wensen, en omgezet in artikelvorm.

Succes met trainen!

## Bereken tempo met afstand en tijd

Als je weet hoe ver je loopt in een bepaalde tijd, kan je je tempo berekenen. **Een lager getal is sneller.** De formule is als volgt: $\text{tempo} = \frac{\text{tijd}}{\text{afstand} / 1000}$.

<label for="distance">Afstand (meters): </label>
<input type="number" id="distance" placeholder="600" oninput="calculatePace()">

<label for="time">Tijd in minuten: </span></label>
<input type="number" id="time" placeholder="3" oninput="calculatePace()">

<p id="paceResult">Resultaat:</p>

## Converteer km/h naar min/km

De formule is als volgt: $\text{tempo} = \frac{60}{\text{snelheid}}$. **Een lager getal is sneller.**

<label for="kmph">Snelheid (km/h): </label>
<input type="number" id="kmph" step="0.1" placeholder="12,5" oninput="convertKmphToMinPerKm()">

<p id="kmphResult">Resultaat:</p>

## Converteer min/km naar km/h

De formule voor tempo naar snelheid in kilometer per uur is als volgt: $\text{snelheid} = \frac{60}{\text{tempo}}$. **Een hoger getal is sneller.**

<label for="minPerKm">Tempo (min/km): </label>
<input type="text" id="minPerKm" placeholder="4:59" oninput="convertMinPerKmToKmph()">
<p id="minPerKmResult">Resultaat:</p>


Credits foto: [Mateusz Dach](https://www.pexels.com/photo/blue-athletic-field-332835/)

<style>
    /* Hack to save my eyes */
    @media (prefers-color-scheme: dark) {
        input {
            background-color: #333;
            color: white;
            border: 1px solid #555;
        }
    }
</style>

<script>
    function calculatePace() {
        const distance = document.getElementById('distance').value;
        const time = document.getElementById('time').value;
        if (distance > 0 && time > 0) {
            const pace = (time / (distance / 1000)).toFixed(2);
            document.getElementById('paceResult').innerText = `Resultaat: ${pace} min/km`;
        } else {
            document.getElementById('paceResult').innerText = 'Resultaat:';
        }
    }

    function convertKmphToMinPerKm() {
        const kmph = document.getElementById('kmph').value;
        if (kmph > 0) {
            const minPerKm = (60 / kmph).toFixed(2);
            document.getElementById('kmphResult').innerText = `Resultaat: ${minPerKm} min/km`;
        } else {
            document.getElementById('kmphResult').innerText = 'Resultaat:';
        }
    }

    function convertMinPerKmToKmph() {
        const minPerKm = document.getElementById('minPerKm').value;
        let minSecArray = minPerKm.split(':');
        let minutes, seconds = 0;

        if (minSecArray.length === 2) {
            minutes = parseInt(minSecArray[0]);
            seconds = parseInt(minSecArray[1]);
        } else if (minSecArray.length === 1) {
            minutes = parseFloat(minPerKm.replace(',', '.'));
        } else {
            document.getElementById('minPerKmResult').innerText = 'Resultaat:';
            return;
        }

        if (minutes >= 0 && (seconds >= 0 && seconds < 60)) {
            let totalMinutes = minutes + (seconds / 60);
            const kmph = (60 / totalMinutes).toFixed(2);
            document.getElementById('minPerKmResult').innerText = `Resultaat: ${kmph} km/h`;
        } else {
            document.getElementById('minPerKmResult').innerText = 'Resultaat:';
        }
    }
</script>
