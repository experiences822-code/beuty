# NÁCAR BEAUTY · Arquitectura base v0.1

Stack:
- Frontend: HTML5 + CSS3 + JavaScript vanilla.
- Backend: Node.js + Express.
- Datos: Supabase PostgreSQL.
- Estilo: responsive, mobile-first, glassmorphism, palo de rosa, marfil, tonos tierra y detalles dorados.

## Ejecutar en local
1. Instalar Node.js LTS.
2. Abrir esta carpeta en VS Code.
3. Ejecutar `npm install`.
4. Copiar `.env.example` como `.env`.
5. Para una demo visual sin Supabase, dejar las variables de Supabase vacías.
6. Ejecutar `npm run dev`.
7. Abrir `http://localhost:3000`.

La demo ofrece servicios de muestra y permite enviar una solicitud a WhatsApp. Si Supabase no está configurado, la API responde en modo demo y avisa que la cita no se guardó en una base compartida.

## Conectar Supabase
1. Crear un proyecto en Supabase.
2. Abrir SQL Editor y ejecutar `supabase/schema.sql`.
3. Copiar Project URL y Service Role key a `.env`.
4. Reiniciar el servidor.

IMPORTANTE:
- La Service Role key es secreta: solo se usa en Node.js, nunca en `public/`, HTML o JS del navegador.
- El esquema activa RLS. El backend inicial accede mediante service role y no expone las tablas al navegador.
- Antes de producción: implementar Supabase Auth para administración, políticas RLS por rol, rate limiting, validación robusta, protección anti-spam, manejo de zona horaria y una reserva transaccional que evite dobles reservas.
- La disponibilidad incluida es un prototipo de franjas horarias; aún no calcula conflictos por duración, profesional ni pausas. Debe completarse antes de aceptar reservas reales.

## Módulos de datos creados
- customers
- professionals
- services
- professional_services
- professional_schedules
- appointments
- products
- sales
- sale_items

## Próximas etapas sugeridas
1. Panel privado y autenticación por roles.
2. Agenda visual por profesional y duración real de servicio.
3. Inventario con entradas, salidas y alertas de stock.
4. Ventas y detalle de caja.
5. Storage para fotos y portafolio.
6. Reportes e indicadores.
