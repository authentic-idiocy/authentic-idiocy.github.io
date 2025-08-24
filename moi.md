---
layout: default
title: Moi
---

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 220 180" width="440" height="360" aria-label="Animated mound pop + tomb rise + bouquets from above">
  <defs>
    <path id="stonePath" d="M50 150 V76 A60 60 0 0 1 170 76 V150 Z"/>
    <clipPath id="clip"><use href="#stonePath"/></clipPath>

    <filter id="pinkGlow" x="-40%" y="-40%" width="180%" height="180%">
      <feDropShadow dx="0" dy="0" stdDeviation="2.6" flood-color="#FF00A0" flood-opacity="0.95"/>
    </filter>
    <filter id="extrude" x="-40%" y="-40%" width="180%" height="180%">
      <feOffset in="SourceAlpha" dx="5" dy="5" result="off"/>
      <feGaussianBlur in="off" stdDeviation="0.8" result="blur"/>
      <feFlood flood-color="#6C00E0" result="color"/>
      <feComposite in="color" in2="blur" operator="in" result="shadow"/>
      <feMerge><feMergeNode in="shadow"/></feMerge>
    </filter>

    <!-- Bouquet symbol (white petals w/ hot-pink glow, purple stems) -->
    <g id="bouquet" stroke-linecap="round">
      <!-- stems -->
      <g stroke="#6C00E0" stroke-width="2">
        <line x1="0" y1="0" x2="22" y2="6"/>
        <line x1="0" y1="0" x2="22" y2="0"/>
        <line x1="0" y1="0" x2="22" y2="-6"/>
      </g>
      <!-- ribbon -->
      <ellipse cx="2" cy="0" rx="3.5" ry="2.2" fill="#FF00A0" opacity="0.9"/>
      <!-- flowers -->
      <g fill="#fff" stroke="#FF00A0" filter="url(#pinkGlow)">
        <!-- left -->
        <g transform="translate(22,6) scale(1.15)">
          <circle r="3"/><circle cx="2.6" cy="0" r="2.2"/><circle cx="-2.6" cy="0" r="2.2"/>
          <circle cx="0" cy="2.6" r="2.2"/><circle cx="0" cy="-2.6" r="2.2"/>
          <circle cx="0" cy="0" r="1.2" fill="#6C00E0"/>
        </g>
        <!-- middle -->
        <g transform="translate(22,0) scale(1.35)">
          <circle r="3"/><circle cx="2.6" cy="0" r="2.2"/><circle cx="-2.6" cy="0" r="2.2"/>
          <circle cx="0" cy="2.6" r="2.2"/><circle cx="0" cy="-2.6" r="2.2"/>
          <circle cx="0" cy="0" r="1.2" fill="#6C00E0"/>
        </g>
        <!-- right -->
        <g transform="translate(22,-6) scale(1.05)">
          <circle r="3"/><circle cx="2.6" cy="0" r="2.2"/><circle cx="-2.6" cy="0" r="2.2"/>
          <circle cx="0" cy="2.6" r="2.2"/><circle cx="0" cy="-2.6" r="2.2"/>
          <circle cx="0" cy="0" r="1.2" fill="#6C00E0"/>
        </g>
      </g>
    </g>

    <style>
      text { font-family: ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, Arial, "Helvetica Neue", Helvetica, "Noto Sans", Ubuntu, Cantarell, sans-serif; }
    </style>
  </defs>

  <!-- Tombstone (draw FIRST so mound can cover base) -->
  <g id="stone" transform="translate(0,22)" opacity="0">
    <use href="#stonePath" fill="none" stroke="#6C00E0" stroke-width="8" filter="url(#extrude)" opacity="0.9"/>
    <use href="#stonePath" fill="none" stroke="#FF00A0" stroke-width="4" stroke-linejoin="round" filter="url(#pinkGlow)"/>
    <g clip-path="url(#clip)" filter="url(#pinkGlow)">
      <g fill="#FF00A0" text-anchor="middle">
        <text x="110" y="70"  font-size="16" font-weight="900" textLength="110" lengthAdjust="spacingAndGlyphs">HERE LIES</text>
        <text x="110" y="85"  font-size="11" font-weight="800" textLength="110" lengthAdjust="spacingAndGlyphs">SHWETHA P. BHARADWAJ&#39;s</text>
        <text x="110" y="105" font-size="16" font-weight="900" textLength="100" lengthAdjust="spacingAndGlyphs">HOPES</text>
        <text x="110" y="120" font-size="16" font-weight="900" textLength="30"  lengthAdjust="spacingAndGlyphs">AND</text>
        <text x="110" y="135" font-size="16" font-weight="900" textLength="110" lengthAdjust="spacingAndGlyphs">DREAMS</text>
      </g>
    </g>
    <animateTransform attributeName="transform" type="translate" dur="0.82s"
      values="0,22; 0,-3; 0,-13" keyTimes="0;.6;1" begin="0.18s" fill="freeze"/>
    <animate attributeName="opacity" dur="0.4s" values="0;1" begin="0.18s" fill="freeze"/>
  </g>

  <!-- Mound (front of stone) -->
  <g id="mound" transform="translate(6,8) scale(0.94,1.06)">
    <path d="M40 140
             C 55 131, 70 127, 86 129
             C 96 126, 114 125, 128 129
             C 142 127, 158 131, 168 140
             L 168 150 40 150 Z"
          fill="#6C00E0" stroke="#FF00A0" stroke-width="3" filter="url(#pinkGlow)"/>
    <!-- dirt flecks -->
    <g fill="#FF00A0" opacity="0">
      <circle cx="82" cy="136" r="1.7">
        <animateTransform attributeName="transform" type="translate" dur="0.9s" values="0,0; -18,-24" begin="0.12s" fill="freeze"/>
        <animate attributeName="opacity" dur="0.9s" values="0;1;0" begin="0.12s" fill="freeze"/>
      </circle>
      <circle cx="138" cy="136" r="1.4">
        <animateTransform attributeName="transform" type="translate" dur="0.9s" values="0,0; 0,-22" begin="0.16s" fill="freeze"/>
        <animate attributeName="opacity" dur="0.9s" values="0;1;0" begin="0.16s" fill="freeze"/>
      </circle>
      <circle cx="110" cy="138" r="1.2">
        <animateTransform attributeName="transform" type="translate" dur="0.9s" values="0,0; 16,-26" begin="0.20s" fill="freeze"/>
        <animate attributeName="opacity" dur="0.9s" values="0;1;0" begin="0.20s" fill="freeze"/>
      </circle>
    </g>
    <animateTransform attributeName="transform" type="translate" dur="0.6s"
      values="6,8; 7,0; 7,0" keyTimes="0;.7;1" begin="0s" fill="freeze"/>
    <animate attributeName="opacity" dur="0.3s" values="0;1" begin="0s" fill="freeze"/>
  </g>

  <!-- Bouquets dropped from above (draw LAST so they sit on top of the mound) -->
  <!-- Landing Y ≈ 134–136 (crest area). Tweak X to taste. -->
  <g filter="url(#pinkGlow)">
    <!-- Bouquet A -->
    <g transform="translate(88,-40) rotate(-18)" opacity="0">
      <use href="#bouquet"/>
      <animate attributeName="opacity" begin="1.05s" dur="0.06s" values="0;1" fill="freeze"/>
      <!-- drop + bounce -->
      <animateTransform attributeName="transform" type="translate" begin="1.05s" dur="0.95s" fill="freeze"
        values="88,-40; 88,134; 88,128; 88,144" keyTimes="0;.78;.88;1"/>
      <animateTransform attributeName="transform" additive="sum" type="rotate" begin="1.05s" dur="0.95s" fill="freeze"
        values="-18; -26; -20; -22" keyTimes="0;.78;.88;1"/>
    </g>

    <!-- Bouquet B -->
    <g transform="translate(110,-50) rotate(-10)" opacity="0">
      <use href="#bouquet"/>
      <animate attributeName="opacity" begin="1.18s" dur="0.06s" values="0;1" fill="freeze"/>
      <animateTransform attributeName="transform" type="translate" begin="1.18s" dur="1.0s" fill="freeze"
        values="110,-50; 110,132; 110,126; 110,147" keyTimes="0;.78;.88;1"/>
      <animateTransform attributeName="transform" additive="sum" type="rotate" begin="1.18s" dur="1.0s" fill="freeze"
        values="-10; -24; -16; -20" keyTimes="0;.78;.88;1"/>
    </g>

    <!-- Bouquet C -->
    <g transform="translate(132,-44) rotate(-24)" opacity="0">
      <use href="#bouquet"/>
      <animate attributeName="opacity" begin="1.32s" dur="0.06s" values="0;1" fill="freeze"/>
      <animateTransform attributeName="transform" type="translate" begin="1.32s" dur="0.95s" fill="freeze"
        values="132,-44; 132,136; 132,130; 132,145" keyTimes="0;.78;.88;1"/>
      <animateTransform attributeName="transform" additive="sum" type="rotate" begin="1.32s" dur="0.95s" fill="freeze"
        values="-24; -28; -22; -24" keyTimes="0;.78;.88;1"/>
    </g>
  </g>
</svg>
