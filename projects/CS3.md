---
layout: project
type: project
image: img/ESUS/STM_hero.png
title: "3U CubeSat: ESUS"
permalink: /projects/CS3/
start_date: January 2023
end_date: July 2024
published: true
summary: "Built the flight-representative mechanical CAD of a 3U CubeSat and derived the first Structural & Thermal Model (STM) to validate Phase B through deployer compatibility and mass-property verification."
period: CentraleSupélec Space Center for CubeSats
---

<div class="container py-3">

<p>
<strong>Program:</strong> CentraleSupélec 3U CubeSat (ESUS)<br>
<strong>Sponsors / Technical support:</strong> French Space Agency (CNES), Thales Alenia Space<br>
<strong>Role:</strong> Structure & Thermal team (2 people) — I led structural work; teammate led thermal (tight coordination)
</p>

<!-- STM hero (open + closed) -->
<div style="display:flex; gap:1rem; flex-wrap:wrap; justify-content:center; align-items:flex-start;">
  <div style="max-width: 420px; flex: 1 1 320px; text-align:center;">
    <img src="{{ '/img/ESUS/ESUS_STM1.jpg' | relative_url }}" alt="ESUS STM — open configuration" style="width:100%; height:auto; margin: 1rem auto; display:block;">
    <span style="font-size: 0.9rem; color: gray; display:block; text-align:center;">Figure 1a — ESUS STM (open configuration).</span>
  </div>
  <div style="max-width: 420px; flex: 1 1 320px; text-align:center;">
    <img src="{{ '/img/ESUS/ESUS_STM2.png' | relative_url }}" alt="ESUS STM — closed configuration" style="width:100%; height:auto; margin: 1rem auto; display:block;">
    <span style="font-size: 0.9rem; color: gray; display:block; text-align:center;">Figure 1b — ESUS STM (closed configuration).</span>
  </div>
</div>

<hr>

<h4>Objective</h4>
<p>
ESUS is a CentraleSupelec 3U CubeSat scheduled for launch in 2027, developed end-to-end by a team of ~30 engineering students and 5 faculty advisors, with sponsorship and technical support from the French Space Agency and Thales Alenia Space. The mission carries two payloads:
</p>

<ul>
  <li>an interferometer to measure the Sun’s diameter,</li>
  <li>an AI camera that analyzes images onboard and discards frames with excessive cloud cover to reduce memory and power usage.</li>
</ul>

<p>
Along with one other student, we formed the Structure & Thermal team. I was primarily responsible for the structural work, while my teammate focused on thermal aspects; however, the two domains were tightly coupled and required coordination. I built the flight-representative mechanical CAD of ESUS and derived from it the first Structural & Thermal Model (STM) to validate Phase B (Preliminary Design & Technology Completion) through mechanical qualification activities.
</p>

<hr>

<h4>STM requirements</h4>
<ul>
  <li><strong>Form factor:</strong> compliant with a 3U envelope (340.5 × 100 × 100 mm) and compatible with P-POD-class interfaces via the ISIS iSiPod deployer.</li>
  <li><strong>Mechanical representativeness:</strong> replicate the mass distribution and equivalent inertia of the flight configuration.</li>
</ul>

<h4>Success criteria</h4>
<ul>
  <li>Same external geometry and interface features as the flight configuration.</li>
  <li>Equivalent system-level mass and inertia behavior and consistent subsystem placement, sufficient to replicate launch and on-orbit mechanical loads.</li>
</ul>

<hr>

<h4>1) Flight CAD architecture</h4>
<p>
I first created a full flight-representative CAD baseline of ESUS using real subsystem geometry—some provided by CNES, and some produced internally (by other students for the payload for example) or by me. This CAD was used to:
</p>

<ul>
  <li>lock deployer interfaces and critical tolerance stack-ups (rails/panels/fasteners) to guarantee clearance and reliable ejection,</li>
  <li>converge subsystem packaging and stack-up to meet mass distribution constraints, ensure connectivity between components, and account for thermal transfer considerations,</li>
  <li>establish the mass-property targets that the STM would need to reproduce,</li>
  <li>prepare the build of the flight model.</li>
</ul>

<!-- Flight CAD visuals -->
<div style="display:flex; gap:1rem; flex-wrap:wrap; justify-content:center; align-items:flex-start;">
  <div style="max-width: 420px; flex: 1 1 320px; text-align:center;">
    <img src="{{ '/img/ESUS/CAD_STM%20COMPLET%20OUVERT.jpg' | relative_url }}" alt="Flight CAD — full mechanical assembly" style="width:100%; height:auto; margin: 1rem auto; display:block;">
    <span style="font-size: 0.9rem; color: gray; display:block; text-align:center;">Figure 2 — Flight CAD: full mechanical assembly (open view).</span>
  </div>
  <div style="max-width: 420px; flex: 1 1 320px; text-align:center;">
    <img src="{{ '/img/ESUS/CAD_ferme%20panneau%20solaire.jpg' | relative_url }}" alt="Flight CAD — external panels and solar panel layout" style="width:100%; height:auto; margin: 1rem auto; display:block;">
    <span style="font-size: 0.9rem; color: gray; display:block; text-align:center;">Figure 3 — Flight CAD: external panels and solar panel layout (interface-driven geometry).</span>
  </div>
</div>

<hr>

<h4>2) From CAD to STM: why mass dummies were necessary</h4>

<p><strong>The problem we had to solve</strong><br>
During Phase B, several flight components were not yet physically available—especially items provided by CNES and parts of the payload—although we did have the mechanical information needed to model them. Waiting for all flight hardware would have delayed system-level verification by months to years, preventing timely Phase B validation with sponsors.
</p>

<p><strong>The decision</strong><br>
I used mass dummies as an engineering solution. Even without final hardware, this approach allowed us to validate the mechanical aspects for Phase B:
</p>

<ul>
  <li>deployer interface compatibility and ejection behavior,</li>
  <li>vibration survivability and structural integrity trends (launcher-driven requirements),</li>
  <li>global mass properties (total mass, center of gravity, and inertia behavior).</li>
</ul>

<p>
To make the STM representative, dummy masses were sized using datasheet component masses. Their placement followed the real component layout on PCBs, and shapes were sometimes tuned (plates, blocks, butterfly geometries) to better reproduce inertia behavior rather than only matching total mass. This required that I manufactured aluminum or steel parts depending on the required density, using CentraleSupelec’s fabrication laboratory, including:
</p>

<ul>
  <li>waterjet cutting,</li>
  <li>laser cutting (CO<sub>2</sub> and fiber),</li>
  <li>3D printing (filament and resin) for smaller parts.</li>
</ul>

<!-- Mass dummy + rack CAD -->
<div style="display:flex; gap:1rem; flex-wrap:wrap; justify-content:center; align-items:flex-start;">
  <div style="max-width: 420px; flex: 1 1 320px; text-align:center;">
    <img src="{{ '/img/ESUS/Ninao%20de%20CNES%20(forme%20papillions).png' | relative_url }}" alt="Example mass dummy tuned for inertia: butterfly-shaped geometry" style="width:100%; height:auto; margin: 1rem auto; display:block;">
    <span style="font-size: 0.9rem; color: gray; display:block; text-align:center;">Figure 4 — Example mass dummy (butterfly geometry) tuned to better match inertia behavior.</span>
  </div>
  <div style="max-width: 420px; flex: 1 1 320px; text-align:center;">
    <img src="{{ '/img/ESUS/CAD_Rack_carte.png' | relative_url }}" alt="CAD — card rack stack-up with PC104 spacing logic" style="width:100%; height:auto; margin: 1rem auto; display:block;">
    <span style="font-size: 0.9rem; color: gray; display:block; text-align:center;">Figure 5 — CAD: avionics/card rack stack-up (PC104 spacing + threaded-rod architecture).</span>
  </div>
</div>

<hr>

<h4>3) STM definition, build, and integration</h4>
<p>The STM reproduces the CubeSat partitioning of the flight design:</p>

<ul>
  <li>a primary structure (4 aluminum rails and 4 aluminum frames),</li>
  <li>a card rack represented by steel/aluminum mass dummies mounted on PCB cards (stacked using M3 threaded rods with PC104 spacing logic),</li>
  <li>payload representation using aluminum/steel masses,</li>
  <li>PCB solar panels mounted on the lateral faces,</li>
  <li>S-band antennas represented by steel masses mounted on external aluminum panels.</li>
</ul>

<!-- STM internal views -->
<div style="display:flex; gap:1rem; flex-wrap:wrap; justify-content:center; align-items:flex-start;">
  <div style="max-width: 420px; flex: 1 1 320px; text-align:center;">
    <img src="{{ '/img/ESUS/STM%20ouvert%20complet.png' | relative_url }}" alt="STM open — internal stack and structure" style="width:100%; height:auto; margin: 1rem auto; display:block;">
    <span style="font-size: 0.9rem; color: gray; display:block; text-align:center;">Figure 6 — STM open: internal stack, mass dummies, and flight-like integration.</span>
  </div>
  <div style="max-width: 420px; flex: 1 1 320px; text-align:center;">
    <img src="{{ '/img/ESUS/RAck%20Carte%20profil%20.png' | relative_url }}" alt="STM rack — profile view showing stack-up" style="width:100%; height:auto; margin: 1rem auto; display:block;">
    <span style="font-size: 0.9rem; color: gray; display:block; text-align:center;">Figure 7 — Rack profile view: card spacing, interfaces, and stack-up coherence.</span>
  </div>
</div>

<hr>

<h4>4) Results</h4>
<p>
Thanks to the STM, we obtained experimental measurements of the system mass and center of gravity location. Using the assembled STM, we measured:
</p>

<ul>
  <li><strong>Total mass:</strong> 2998 g (target was 3 kg)</li>
  <li><strong>Center of gravity offset relative to the structural geometric center:</strong> x = 0 mm, y = 2 mm, z = 7 mm</li>
</ul>

<p><strong>Compliance with iSiPod requirements</strong><br>
According to iSiPod specifications, the center of gravity must lie within a 20 × 20 × 60 mm rectangular box around the geometric center. Our measured center of gravity falls comfortably inside this volume, providing strong evidence that the mass-dummy strategy was effective and that the STM is representative enough to support meaningful deployer and qualification testing.
</p>

<p>
With this STM now representative of the flight configuration, we can proceed with mechanical testing and use the results to support Phase B validation, provided test outcomes meet expectations.
</p>

</div>
