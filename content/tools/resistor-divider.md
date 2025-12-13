---
title: "Resistor Divider Calculator"
date: 2024-11-25
---

Quick calculator for voltage divider circuits. Useful for setting reference voltages or scaling analog inputs.

<div class="tool-embed calculator">
    <h3>Calculate Output Voltage</h3>
    <label for="vin">Input Voltage (V):</label>
    <input type="number" id="vin" value="5" step="0.1">
    
    <label for="r1">R1 (Ω):</label>
    <input type="number" id="r1" value="10000" step="100">
    
    <label for="r2">R2 (Ω):</label>
    <input type="number" id="r2" value="10000" step="100">
    
    <button onclick="calculateDivider()">Calculate</button>
    
    <div id="result" class="result" style="display:none;"></div>
</div>

<script>
function calculateDivider() {
    const vin = parseFloat(document.getElementById('vin').value);
    const r1 = parseFloat(document.getElementById('r1').value);
    const r2 = parseFloat(document.getElementById('r2').value);
    
    if (isNaN(vin) || isNaN(r1) || isNaN(r2) || r1 <= 0 || r2 <= 0) {
        alert('Please enter valid positive numbers');
        return;
    }
    
    const vout = vin * (r2 / (r1 + r2));
    const current = vin / (r1 + r2) * 1000; // in mA
    const power = (vin * vin) / (r1 + r2) * 1000; // in mW
    
    const resultDiv = document.getElementById('result');
    resultDiv.innerHTML = `
        <strong>Output Voltage:</strong> ${vout.toFixed(3)} V<br>
        <strong>Current:</strong> ${current.toFixed(3)} mA<br>
        <strong>Total Power:</strong> ${power.toFixed(2)} mW
    `;
    resultDiv.style.display = 'block';
}
</script>

## How to use

Enter your input voltage and resistor values. The calculator shows the output voltage, current draw, and power dissipation.

## Notes

This assumes ideal resistors and doesn't account for load impedance. For precision applications, consider resistor tolerances and temperature coefficients.
