<template>
  <div class="background-effect"></div>
</template>

<script setup>
// No necesitamos lógica aquí (el toggle se maneja normalmente con .dark o html.light)
</script>

<style scoped>
.background-effect {
  position: fixed;
  inset: 0;
  z-index: -2;
  pointer-events: none;
  overflow: hidden;

  /* ── Variables base ── */
  --dot-size: 7px;
  --transition: 0.5s ease-in-out;   /* tiempo de cambio entre modos */

  background-color: #0a0a0f;
  
  background-image:
    /* Capa de puntitos sutiles (ruido) */
    radial-gradient(circle at 50% 50%, transparent 1.8px, #00000088 0 var(--dot-size), #ffffff08 var(--dot-size)),
    
    /* Gradientes de color base (más suaves) */
    radial-gradient(circle at 30% 70%, #caa7e7, #a855f7 50%, transparent 70%),
    radial-gradient(circle at 70% 30%, #da8db3, #f472b6 55%, transparent 75%),
    radial-gradient(circle at 20% 20%, #9dbaea, #60a5fa 60%, transparent 80%),
    radial-gradient(ellipse at 80% 80%, #a8e4ee, #67e8f9 65%, transparent 85%);

  background-size:
    18px 32px,
    300% 300%,
    280% 280%,
    320% 320%,
    350% 350%;

  background-position: 
    0 0,
    0% 0%,
    100% 100%,
    50% 50%,
    0% 100%;

  /* Animación continua (muy lenta para no marear) */
  animation: 
    drift 90s linear infinite,
    hue-rotate 140s linear infinite;

  /* Transiciones suaves al cambiar modo */
  transition: 
    background-color var(--transition),
    filter var(--transition),
    background-image var(--transition),
    opacity var(--transition);
}

/* ── Modo CLARO ── */
html.light .background-effect,
html:not(.dark) .background-effect {
  background-color: #f8fafc;
  
  background-image:
    radial-gradient(circle at 50% 50%, transparent 2px, #000000f4 0 var(--dot-size), #cbd5e10f var(--dot-size)),
    
    radial-gradient(circle at 40% 60%, #8000ff, #d8b4fe 50%, transparent 70%),
    radial-gradient(circle at 60% 40%, #ff008c, #fbcfe8 55%, transparent 75%),
    radial-gradient(circle at 30% 30%, #0077ff, #bfdbfe 60%, transparent 80%),
    radial-gradient(ellipse at 70% 70%, #00e1fa, #cffafe 65%, transparent 85%);

  filter: brightness(0.98) saturate(0.75);
  animation: 
    drift 120s linear infinite,
    hue-rotate 180s linear infinite;   /* más lento aún en light */
}

/* Animaciones */
@keyframes hue-rotate {
  0%   { filter: hue-rotate(0deg) saturate(0.75); }
  100% { filter: hue-rotate(360deg) saturate(0.75); }
}

@keyframes drift {
  0% {
    background-position: 
      0 0,
      0% 0%,
      100% 100%,
      50% 50%,
      0% 100%;
  }
  100% {
    background-position: 
      0 0,
      200% 200%,
      -150% -150%,
      -180% -180%,
      180% 180%;
  }
}

/* Opcional: si quieres que el cambio sea aún más dramático/suave */
html.light .background-effect {
  opacity: 0.92;
}

.dark .background-effect {
  opacity: 1;
}
</style>