El reto: crear un CNE que sí funcione y muestre las actas.

Nuestra solución: implementar una blockchain.

# Sistema Electoral Basado en Blockchain

## **Enunciado del Proyecto**

### **El nuevo CNE**

**Contexto:** En el marco de la modernización del sistema electoral, se requiere desarrollar un prototipo de votación digital que garantice transparencia, seguridad e inmutabilidad mediante tecnología blockchain.

**Objetivo:** Crear un sistema donde cada voto sea registrado como una transacción en una blockchain privada, permitiendo:
- Verificación pública de la integridad del proceso
- Anonimato del votante preservado mediante criptografía
- Trazabilidad completa sin comprometer la privacidad
- Conteo automático y auditable

**Requisitos:**
1. Solo votantes autorizados pueden emitir votos
2. Cada persona solo puede votar una vez
3. Los votos son anónimos pero verificables
4. La cadena de bloques debe ser resistente a modificaciones
5. Interfaz simple para votantes y administradores

## **Módulos del Sistema**

### **1. Módulo de Identidad y Autenticación**

- Registro y verificación de votantes
- Generación de credenciales únicas
- Sistema de claves públicas/privadas
- Verificación de elegibilidad

Se necesita un algoritmo que permita el registro de una cantidad desconocida de votantes. Debera solicitar el numero de cedula, el nombre, el apellido y una firma (resultante )

### **2. Módulo de Emisión de Votos**

- Interfaz de votación
- Firma digital del voto
- Cifrado del contenido
- Generación de transacciones
- Confirmación de voto único

### **3. Módulo Blockchain Core**

- Estructura de bloques (Block)
- Cadena de bloques (Blockchain)
- Mecanismo de consenso (Proof-of-Authority)
- Validación de transacciones
- Minería/creación de nuevos bloques

### **4. Módulo de Transacciones**

- Estructura de transacción de voto
- Validación de firma digital
- Verificación de integridad
- Timestamp y metadatos

### **5. Módulo de Conteo y Resultados**

- Conteo de votos desde la blockchain
- Verificación de resultados
- Generación de estadísticas
- Exportación de datos

### **6. Módulo de Auditoría**

- Verificación de integridad de la cadena
- Herramientas de transparencia
- Logs del sistema
- Verificación individual de votos

### **7. Módulo de Interfaz**

- Interfaz web para votantes
- Panel de administración
- Visualización de resultados
- Herramientas de verificación

## **Flujo del Sistema**

1. **Registro**: Votante se autentica y recibe credenciales
2. **Votación**: Votante emite voto firmado digitalmente
3. **Transacción**: Voto se añade a transacciones pendientes
4. **Minado**: Transacciones se validan y se crea nuevo bloque
5. **Verificación**: Bloque se añade a la cadena
6. **Conteo**: Resultados se calculan desde la cadena
7. **Auditoría**: Cualquier persona puede verificar la cadena
