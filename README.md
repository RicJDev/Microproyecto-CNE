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

### Blockchain Core

- Incluye funciones para hashear, comparar hashes y comprobar la integridad de la cadena de bloques

### Votantes

- Incluye el registro de los ciudadanos con derecho al voto.
- Utiliza una firma personal cifrada para simular la verificacion biometrica de nuestro sistema electoral

### Candidatos

- Registro de los mentiro... ejem... de los candidatos, con sus respectivos partidos politicos.

### Votos

- Interfaz para que el usuario pueda ejercer su derecho al voto. Aca es donde el usurio puede elegir su candidato, asegurando que solo lo haga una unica vez

### Resultados

- Y aqui esta la chicha: las actas. Se incluye un metodo de verificacion utilizando el Blockchain Core

## Y como siempre, el árbol de archivo

```
.
├── README.md
└── src
    ├── blockchain-core
    │   ├── hash.gabo
    │   ├── validar_cadena.gabo
    │   └── validar_hash.gabo
    ├── candidatos
    │   ├── cargar_candidatos.gabo
    │   └── mostrar_candidatos.gabo
    ├── principal.gabo
    ├── resultados
    │   ├── resultados.gabo
    │   └── validar_resultados.gabo
    ├── votantes
    │   └── Usuarios.gabo
    └── votos
        ├── CifradoYFirma.gabo
        ├── ConfigInicial.gabo
        ├── EmisionVotos.gabo
        ├── GenerarTransaccion.gabo
        ├── GuardarEnLedger.gabo
        ├── ImpresionComprobante.gabo
        └── VerificarUnicidad.gabo
```
