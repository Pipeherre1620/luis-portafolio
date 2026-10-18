<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 900 300" width="100%" height="100%">
  <defs>
    <!-- Degradado sutil para el icono -->
    <linearGradient id="capGradient" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" stop-color="#1F2937" />
      <stop offset="100%" stop-color="#111827" />
    </linearGradient>

    <!-- Resplandor sutil para el acento mint/verde -->
    <filter id="mintGlow" x="-20%" y="-20%" width="140%" height="140%">
      <feDropShadow dx="0" dy="2" stdDeviation="4" flood-color="#00E676" flood-opacity="0.35"/>
    </filter>
  </defs>

  <!-- Fondo oscuro fintech -->
  <rect width="900" height="300" rx="20" fill="#0D1117" />

  <!-- ==================== GRUPO ISOTIPO (GORRA HERREFINANCE) ==================== -->
  <g transform="translate(60, 40)">
    <!-- Base / Sombra suave inferior -->
    <ellipse cx="110" cy="205" rx="95" ry="10" fill="#000000" opacity="0.45" />

    <!-- Visera de la gorra -->
    <path d="M 12 172 C 35 158, 185 158, 208 172 C 218 178, 195 192, 110 192 C 25 192, 2 178, 12 172 Z"
          fill="#1F2937" stroke="#374151" stroke-width="3" stroke-linejoin="round" />

    <!-- Corona / Domo de la gorra -->
    <path d="M 28 165 C 26 80, 70 30, 110 30 C 150 30, 194 80, 192 165 Z"
          fill="url(#capGradient)" stroke="#374151" stroke-width="3" stroke-linejoin="round" />

    <!-- Botón superior -->
    <ellipse cx="110" cy="30" rx="11" ry="5.5" fill="#374151" />

    <!-- Contorno / Ribete de la visera -->
    <path d="M 18 174 C 45 163, 175 163, 202 174"
          fill="none" stroke="#4B5563" stroke-width="2.5" stroke-linecap="round" />

    <!-- Glifo central: Llaves de código dev + Signo de dinero fintech -->
    <g filter="url(#mintGlow)" transform="translate(110, 116)" text-anchor="middle" dominant-baseline="central">
      <!-- Llave izquierda -->
      <text x="-42" y="-2" fill="#F3F4F6" font-family="monospace, 'Fira Code', 'JetBrains Mono', Courier" font-size="44" font-weight="700">{</text>
      <!-- Símbolo de dinero ($) en verde neón -->
      <text x="0" y="-1" fill="#00E676" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Montserrat, sans-serif" font-size="40" font-weight="900">$</text>
      <!-- Llave derecha -->
      <text x="42" y="-2" fill="#F3F4F6" font-family="monospace, 'Fira Code', 'JetBrains Mono', Courier" font-size="44" font-weight="700">}</text>
    </g>
  </g>

  <!-- ==================== GRUPO LOGOTIPO (TEXTO HERREFINANCE) ==================== -->
  <g transform="translate(320, 162)">
    <!-- HERRE: Extra Bold blanco -->
    <text x="0" y="0"
          fill="#F9FAFB"
          font-family="-apple-system, BlinkMacSystemFont, 'Montserrat', 'Inter', 'Segoe UI', sans-serif"
          font-size="64"
          font-weight="900"
          letter-spacing="2">HERRE</text>

    <!-- FINANCE: Regular / Acento verde -->
    <text x="246" y="0"
          fill="#00E676"
          font-family="-apple-system, BlinkMacSystemFont, 'Montserrat', 'Inter', 'Segoe UI', sans-serif"
          font-size="64"
          font-weight="400"
          letter-spacing="4">FINANCE</text>

    <!-- Subtítulo descriptivo / Firma de marca -->
    <text x="4" y="38"
          fill="#8B949E"
          font-family="-apple-system, BlinkMacSystemFont, 'Inter', 'Segoe UI', sans-serif"
          font-size="15"
          font-weight="600"
          letter-spacing="5">BY PIPE HERRE • SMART TECH ASSETS</text>
  </g>
</svg>