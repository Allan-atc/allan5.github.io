---
layout: project
type: project
image: img/ESUS_STM/stm_assembled.png
title: "CubeSat 3U STM"
start_date: 2024-01 # adjust
end_date: 2024-06   # adjust
published: true
labels:
  - SolidWorks
  - CAD
  - Mechanical Integration
  - CubeSat 3U
  - Mass Properties
  - P-POD / iSiPod
  - Assembly
summary: "Structural–Thermal Model (STM) of a 3U CubeSat, representative in mass and inertia, built to verify deployment interfaces and qualify vibration and test readiness."
period: CubeSat Program / Academic Project
---

<div class="container py-3">

<h3>ESUS — 3U CubeSat Structural–Thermal Model (STM)</h3>

<p>
<strong>Project goal:</strong> build a Structural–Thermal Model representative in <strong>mass</strong> and <strong>inertia</strong> of the ESUS flight model, enabling mechanical interface checks, deployment validation, and environmental test preparation.
</p>

<hr>

<h4>What this project needed to achieve</h4>
<ul>
  <li><strong>Mechanical interfaces:</strong> verify compatibility with the <strong>iSiPod</strong> deployer (P-POD compatible).</li>
  <li><strong>Deployment readiness:</strong> enable STM ejection testing from the deployer.</li>
  <li><strong>Environmental readiness:</strong> enable vibration testing on a representative mechanical configuration.</li>
  <li><strong>Instrumentation:</strong> support 0-g acceleration measurements (AC).</li>
  <li><strong>Representativeness requirement:</strong> STM is representative in <strong>mass</strong> and <strong>inertia</strong> of the ESUS flight model (mass distribution matching the real component layout).</li>
</ul>

<hr>

<h4>My role (team project — responsibilities clearly defined)</h4>
<p>
This was a <strong>2-person team</strong> project, with additional components/data coming from the <strong>French Space Agency</strong>.
</p>

<ul>
  <li><strong>Mechanical integration lead:</strong> STM CAD integration and final mechanical assembly of the full 3U stack.</li>
  <li><strong>Mass & inertia representativeness:</strong> definition, sizing, and placement of <strong>mass dummies (ballast blocks)</strong> to match mass properties when real hardware was unavailable or masses were uncertain.</li>
  <li><strong>Problem-solving on missing data:</strong> when component masses were not available or not realistic, I built a practical approach using <strong>assumptions + adjustable ballast</strong> to converge on target mass/inertia while preserving the real layout.</li>
  <li><strong>Interface mindset:</strong> ensured the assembled STM respected CubeSat form factor and deployer constraints (rails, outer envelope, keep-out zones).</li>
</ul>

<p style="font-size: 0.95rem; color: #555;">
(If you want: add 1–2 bullets for the other teammate here, so reviewers immediately see the split. Example: “panel design & manufacturing follow-up”, “PC104 stack integration”, etc.)
</p>

<hr>

<h4>How I approached the problem (process + engineering reasoning)</h4>
<ol>
  <li><strong>Start from requirements:</strong> 3U envelope, deployer interface constraints, and mass/inertia representativeness.</li>
  <li><strong>Decompose the satellite:</strong> structure, card rack, payload, solar panels, safety switches, and S-band antennas.</li>
  <li><strong>Design for test realism:</strong> preserve the physical arrangement of components so the inertia tensor is meaningful, not just the total mass.</li>
  <li><strong>Handle missing/uncertain masses:</strong>
    <ul>
      <li>use datasheets when available,</li>
      <li>when not available, define bounded assumptions,</li>
      <li>close the loop with <strong>tunable ballast blocks</strong> (steel/aluminum) placed where they best match inertia targets.</li>
    </ul>
  </li>
  <li><strong>Build modularly:</strong> each PCB assembled independently, then stacked into U-level modules, then integrated into the full 3U structure.</li>
</ol>

<hr>

<h4>Part 1 — STM definition, CAD design, and construction</h4>

<h5>System overview</h5>
<p>
The ESUS STM follows the 3U CubeSat external standard: <strong>340.5 × 100 × 100 mm</strong>. It is composed of:
</p>
<ul>
  <li><strong>Primary structure:</strong> 4 aluminum rails (commercial skeleton) + 4 aluminum frames.</li>
  <li><strong>Electronics rack:</strong> PCBs + threaded rods + spacers; real components represented by ballast blocks.</li>
  <li><strong>Payload + subsystems:</strong> represented by shaped ballast blocks to preserve inertia.</li>
  <li><strong>Solar panels:</strong> PCB panels and aluminum-backed panels depending on face and antenna mounting.</li>
  <li><strong>Safety switches</strong> integrated on the structure.</li>
  <li><strong>S-band antennas:</strong> represented by aluminum/steel plates mounted on aluminum external panels.</li>
</ul>

<p>
The ballast block masses match the target component masses, and their placement on PCBs matches the real component layout to achieve equivalent inertia properties.
</p>

<h5>Structure selection</h5>
<p>
The structural skeleton is a commercial off-the-shelf CubeSat structure: <strong>SPACEMIND SM03</strong>.
</p>

<p align="center">
  <img src="../img/ESUS_STM/structure_skeleton.png" alt="CubeSat structure skeleton (SPACEMIND SM03)." style="max-width: 780px; margin: 1rem auto; display:block;">
  <span style="font-size: 0.9rem; color: gray;">Structure skeleton (SPACEMIND SM03).</span>
</p>

<h5>External panels</h5>
<ul>
  <li><strong>+Y / -Y faces:</strong> PCB-only panels supporting 6 solar cells. Openings added for harness routing (to be refined in Phase C).</li>
  <li><strong>+Z / -Z faces:</strong> aluminum panels supporting S-band antennas, with solar PCB as an overlay. Openings for harness routing.</li>
</ul>

<p align="center">
  <img src="../img/ESUS_STM/side_view_panels.png" alt="Side view showing panel architecture and interfaces." style="max-width: 900px; margin: 1rem auto; display:block;">
  <span style="font-size: 0.9rem; color: gray;">Side view of structure and external panel stack-up.</span>
</p>

<h5>Caps</h5>
<p>
Each end of the structure is closed with an aluminum machined cap (upper and lower).
</p>

<p align="center">
  <img src="../img/ESUS_STM/caps.png" alt="Upper and lower caps in machined aluminum." style="max-width: 780px; margin: 1rem auto; display:block;">
  <span style="font-size: 0.9rem; color: gray;">Upper and lower caps.</span>
</p>

<h5>Electronics rack (PC104 stack)</h5>
<p>
The rack is an assembly of <strong>8 PCB boards</strong> (92 × 95 mm) plus <strong>one machined aluminum board</strong>, tied together using <strong>4 M3 steel threaded rods</strong>, aluminum spacers, and aluminum frames on +X and -X. The rack is organized into <strong>three U-level modules</strong>, electrically connected using the <strong>PC104 bus</strong>.
</p>

<p align="center">
  <img src="../img/ESUS_STM/rack_view1.png" alt="Electronics rack (view 1)." style="max-width: 900px; margin: 1rem auto; display:block;">
  <span style="font-size: 0.9rem; color: gray;">Electronics rack (view 1).</span>
</p>

<p align="center">
  <img src="../img/ESUS_STM/rack_view2.png" alt="Electronics rack (view 2)." style="max-width: 900px; margin: 1rem auto; display:block;">
  <span style="font-size: 0.9rem; color: gray;">Electronics rack (view 2).</span>
</p>

<h5>Subsystem representativeness (examples)</h5>
<p>
Below are representative examples of how subsystems were modeled using ballast blocks to preserve mass and inertia.
</p>

<ul>
  <li><strong>NUAGES camera:</strong> three stacked aluminum rectangles (100 g total) + steel ballast for PCB (100 g), mounted on standard CubeSat PCB.</li>
  <li><strong>NINANO:</strong> “butterfly” shaped ballast block to match inertia of the real board.</li>
  <li><strong>Magnetorquer:</strong> 55 mm aluminum square plate (1.5 mm thick) on standard PCB.</li>
  <li><strong>Batteries:</strong> two 5 mm steel plates totaling 254 g on standard PCB.</li>
  <li><strong>Reaction wheel:</strong> bracketed assembly; wheel represented by 4 aluminum ballast blocks on aluminum standoffs (separate from PC104 bus).</li>
  <li><strong>S-band:</strong> 3 steel ballast blocks for the radio + antenna masses represented by aluminum/steel plates on +Z/-Z panels.</li>
  <li><strong>MIEL:</strong> two-stage board with added ballast (2 × 50 g).</li>
  <li><strong>XLIM:</strong> two-stage architecture (geometry not final); ballast distribution to reach 200 g; circular extrusion on -Y for fiber optic routing.</li>
</ul>

<div class="row" style="margin-top: 1rem;">
  <div class="col-md-6" style="padding: 0.5rem;">
    <img src="../img/ESUS_STM/solidworks_nuages_mass.png" alt="SolidWorks: NUAGES mass dummy concept." style="width: 100%; border-radius: 10px;">
    <div style="font-size: 0.9rem; color: gray; text-align: center; margin-top: 0.4rem;">SolidWorks — NUAGES ballast concept.</div>
  </div>
  <div class="col-md-6" style="padding: 0.5rem;">
    <img src="../img/ESUS_STM/solidworks_ninano_mass.png" alt="SolidWorks: NINANO inertia-matching ballast geometry." style="width: 100%; border-radius: 10px;">
    <div style="font-size: 0.9rem; color: gray; text-align: center; margin-top: 0.4rem;">SolidWorks — NINANO inertia-matching geometry.</div>
  </div>
</div>

<hr>

<h5>Assembly sequence (what was built, step-by-step)</h5>
<ol>
  <li><strong>PCB-level assembly:</strong> mount steel/aluminum ballast blocks on each PCB per datasheets and target layout, using <strong>M3 fasteners</strong>.</li>
  <li><strong>U-level assembly:</strong> stack boards with <strong>4 threaded rods</strong>; spacing set by aluminum standoffs sized for PC104 connector geometry.</li>
  <li><strong>Electrical continuity:</strong> connect U-level modules using <strong>PC104 connectors</strong>.</li>
  <li><strong>Full 3U integration:</strong> attach the three modules into the structure using the manufacturer’s fasteners; verify safety switch mounting torque/retention.</li>
  <li><strong>Antenna masses:</strong> mount antenna ballast plates on +Z/-Z aluminum panels (M3).</li>
  <li><strong>External panels:</strong> mount aluminum and PCB panels with <strong>M2.5</strong> (and solar PCB as the final overlay layer on aluminum faces).</li>
</ol>

<p align="center">
  <img src="../img/ESUS_STM/stm_assembled.png" alt="Assembled STM of the 3U CubeSat." style="max-width: 900px; margin: 1rem auto; display:block;">
  <span style="font-size: 0.9rem; color: gray;">Assembled STM (3U) — final integrated configuration.</span>
</p>

<hr>

<h4>Part 2 — Verification and test readiness (interfaces, deployment, vibration)</h4>
<p>
The STM was designed specifically to enable the following verification activities:
</p>
<ul>
  <li><strong>Deployer fit-check:</strong> verify rail and envelope compatibility with iSiPod (P-POD compatible).</li>
  <li><strong>Ejection test:</strong> validate mechanical behavior during deployer release.</li>
  <li><strong>Vibration test readiness:</strong> validate mechanical assembly robustness and representativeness for environmental testing.</li>
  <li><strong>0-g acceleration measurement support (AC).</strong></li>
</ul>

<p style="font-size: 0.95rem; color: #555;">
Add your actual test outcomes here (pass/fail, measured margins, key plots). If you share the plots/photos, I can place them exactly where they tell the story best.
</p>

<!-- Example placeholders for test visuals -->
<p align="center">
  <img src="../img/ESUS_STM/deployer_interface.png" alt="Interface check with iSiPod / P-POD constraints." style="max-width: 900px; margin: 1rem auto; display:block;">
  <span style="font-size: 0.9rem; color: gray;">Deployer interface check (rails/envelope/keep-out zones).</span>
</p>

<p align="center">
  <img src="../img/ESUS_STM/vibration_setup.png" alt="Vibration test setup (placeholder)." style="max-width: 900px; margin: 1rem auto; display:block;">
  <span style="font-size: 0.9rem; color: gray;">Vibration test setup (replace with your actual photo + key measured spectra/FRF if available).</span>
</p>

<hr>

<h4>Results and evaluation vs. objectives</h4>
<p>
<strong>Deliverable produced:</strong> a fully assembled 3U STM using a flight-representative architecture (structure, PC104 rack, panels, switches, antennas) designed to be representative in mass and inertia and to support deployer interface verification and environmental test preparation.
</p>

<!-- Fill with your numbers when ready -->
<table style="width:100%; border-collapse: collapse; margin-top: 0.8rem;">
  <tr style="background:#f5f5f5;">
    <th style="border:1px solid #ddd; padding:10px; text-align:left;">Objective</th>
    <th style="border:1px solid #ddd; padding:10px; text-align:left;">Evidence / Metric</th>
    <th style="border:1px solid #ddd; padding:10px; text-align:left;">Status</th>
  </tr>
  <tr>
    <td style="border:1px solid #ddd; padding:10px;">Deployer interface compatibility</td>
    <td style="border:1px solid #ddd; padding:10px;">Fit-check with iSiPod / P-POD constraints (rails/envelope)</td>
    <td style="border:1px solid #ddd; padding:10px;">TBD</td>
  </tr>
  <tr>
    <td style="border:1px solid #ddd; padding:10px;">Representative mass</td>
    <td style="border:1px solid #ddd; padding:10px;">Total mass vs. target flight model (kg) — add measured values</td>
    <td style="border:1px solid #ddd; padding:10px;">TBD</td>
  </tr>
  <tr>
    <td style="border:1px solid #ddd; padding:10px;">Representative inertia</td>
    <td style="border:1px solid #ddd; padding:10px;">Inertia tensor / CG match strategy — add method + results</td>
    <td style="border:1px solid #ddd; padding:10px;">TBD</td>
  </tr>
  <tr>
    <td style="border:1px solid #ddd; padding:10px;">Ejection readiness</td>
    <td style="border:1px solid #ddd; padding:10px;">Ejection test video / key observations</td>
    <td style="border:1px solid #ddd; padding:10px;">TBD</td>
  </tr>
  <tr>
    <td style="border:1px solid #ddd; padding:10px;">Vibration readiness</td>
    <td style="border:1px solid #ddd; padding:10px;">Test setup + key plots (sine/random, FRF, acceleration)</td>
    <td style="border:1px solid #ddd; padding:10px;">TBD</td>
  </tr>
</table>

<p style="margin-top: 0.8rem;">
<strong>Engineering takeaway:</strong> building an STM is not only “making a mockup.” The key is preserving the <em>mass distribution</em> and <em>interfaces</em> so that deployer behavior and vibration results are meaningful. The ballast-driven approach allowed progress despite incomplete hardware maturity, while keeping the model physically representative and test-relevant.
</p>

</div>
