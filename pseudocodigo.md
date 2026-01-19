## Pseudocódigo

```
Algoritmo CNE 2.0
  Registro: Votantes;
    ID: Entero;
    Nombre, Apellido, Cedula: Cadena;
    HaVotado: Booleano;
    LlavePrivada: Cadena;
  Fin_Registro

  Registro: Candidatos;
    ID, Votos: Entero;
    Partido, Nombre: Cadena;
  Fin_Registro

  Registro: CandidatosCopia;
    ID, Votos: Entero;
    Partido, Nombre: Cadena;
  Fin_Registro

  Registro: Voto;
    ID, Candidato, HashActual, HashAnterior: Cadena;
  Fin_Registro
Inicio
  var Votantes: votantes[n_vot];
  var Votos: votos[n_vot];
  var Candidatos: candidatos[n_can];
  var CandidatosCopia: candidatosCopia[n_can];

  var n_vot, n_can: Entero;
  var empezar: Booleano;

  // 0: Sin iniciar
  // 1: En carga de candidatos
  // 2: En carga de votantes
  // 3: En proceso de eleccion
  // 4: En emision de resultados
  var estado_eleccion = 0: Entero;

  Mostrar << "Presione 1 para iniciar las elecciones. 0 Para salir";
  Leer >> empezar;

  Si (empezar = 1) Entonces;
    estado_eleccion = 1;
    Sino
      Mostrar << "Bye, bye, Hawaii!";
  Fin_Si

  cargar_candidatos(
    candidatos[n_presi].ID,
    candidatos[n_presi].Votos,
    candidatos[n_presi].Nombre,
    candidatos[n_presi].Partido,
    n_presi,
    estado_eleccion,
  );
  Mostrar << cargar_candidatos;

  Usuarios(
    // TODO: actualizar los parametros
    estado_eleccion,
  );
  Mostrar << Usuarios;

  votacion(
    // TODO: actualizar los parametros
    estado_eleccion
  );

  Mostrar << votacion;

  Si (estado_eleccion = 4) Entonces;
    resutados(
      candidatos[n_can].Votos,
      candidatos[n_can].Partido,
      candidatos[n_can].Nombre,
      candidatosCopia[n_can].Votos,
      candidatosCopia[n_can].Partido,
      candidatosCopia[n_can].Nombre,
      n_can
    );
  Fin_Si
Fin

Funcion hash(texto: Cadena): Cadena;
Inicio
  var hash_resultante = "": Cadena;
  var hash_numero = 2 ^ 4253 - 1; // Un numero primo bastante grande
  var caracteres[n], c: Caracter;
  var i, m, n: Entero;

  split_string(texto, caracteres[n], n);

  Para (i = 1 Hasta i = n) Hacer;
    c = caracteres[i];
    m = caracter_a_entero(m);
    hash_numero = (hash_numero * 31) + m;
  Fin_Para

  hash_numero = hash_numero MOD (2 ^ 607 - 1);

  texto = entero_a_cadena(hash_numero);

  Mientras (n < 240) Hacer;
    split_string(texto, caracteres[n], n);

    // Iremos metiendo ceros para ajustar la longitud de la cadena
    texto = "0" + texto;
  Fin_Mientras

  hash_resultante = texto;

  Devolver(hash_resultante);
Fin_Funcion

Funcion entero_a_cadena(hash_numero: Entero): Cadena;
Inicio
  var resultado: Cadena;

  // ...

  Devolver(resultado);
Fin_Funcion

Funcion caracter_a_entero(car: Caracter): Entero;
Inicio
  var letras[n_letras]: Caracter;
  var i, n_letras = 63: Entero;

  // Para cualquier otro caracter fuera del alfabeto
  // devolvemos un mismo numero
  var resultado = n_letras + 1: Entero; 

  letras[1] = 'A'; letras[2] = 'B'; letras[3] = 'C';
  letras[4] = 'D'; letras[5] = 'E'; letras[6] = 'F';
  letras[7] = 'G'; letras[8] = 'H'; letras[9] = 'I';
  letras[10] = 'J'; letras[11] = 'K'; letras[12] = 'L';
  letras[13] = 'M'; letras[14] = 'N'; letras[15] = 'O';
  letras[16] = 'P'; letras[17] = 'Q'; letras[18] = 'R';
  letras[19] = 'S'; letras[20] = 'T'; letras[21] = 'U';
  letras[22] = 'V'; letras[23] = 'W'; letras[24] = 'X';
  letras[25] = 'Y'; letras[26] = 'Z'; letras[27] = 'a';
  letras[28] = 'b'; letras[29] = 'c'; letras[30] = 'd';
  letras[31] = 'e'; letras[32] = 'f'; letras[33] = 'g';
  letras[34] = 'h'; letras[35] = 'i'; letras[36] = 'j';
  letras[37] = 'k'; letras[38] = 'l'; letras[39] = 'm';
  letras[40] = 'n'; letras[41] = 'o'; letras[42] = 'p';
  letras[43] = 'q'; letras[44] = 'r'; letras[45] = 's';
  letras[46] = 't'; letras[47] = 'u'; letras[48] = 'v';
  letras[49] = 'w'; letras[50] = 'x'; letras[51] = 'y';
  letras[52] = 'z'; letras[53] = '_'; letras[54] = '1';
  letras[55] = '2'; letras[56] = '3'; letras[57] = '4';
  letras[58] = '5'; letras[59] = '6'; letras[60] = '7';
  letras[61] = '8'; letras[62] = '9'; letras[63] = '0';

  Para (i = 1 Hasta i = n_letras) Hacer;
    Si (letras[i] = car) Entonces;
      resultado = i;
    Fin_Si
  Fin_Para

  Devolver(resultado);
Fin_Funcion

// Que misterio tan misterioso saber de donde proviene esto...

Funcion join_char(caracteres[n]: Caracter, n: Entero): Cadena;
Inicio
  // Una funcion misteriosa que, de forma no determinada aun,
  // consigue realizar la operacion inversa al otro procedimiento
  // misterioso: pasar un arreglo de caracteres a cadena de texto

  // Como avanza la tecnologia, vale...

  // A menos que esto sea valido :D
  // Eso le quita el misterio, pero al menos tiene sentido

  var i: Entero;
  var resultado: Cadena = "";

  Para (i = 1 Hasta i = n) Hacer;
    resultado = resultado + caracteres[i];
  Fin_Para

  Devolver (resultado);
Fin_Funcion

Procedimiento split_string(
  E: texto: Cadena,
  S: caracteres[n]: Caracter,
  E: n: Entero
);
Inicio
  // De alguna manera misteriosa este procedimiento logra convertir
  // una cadena de texto en un arreglo unidimensional de caracteres
  // que queda almacenado en `caracteres[n]`
  // ¿Que no es posible? Todo es posible en la Dimension Desconocida

  // :D
Fin_Procedimiento

Funcion validar_cadena(
  votos[n_vot].HashActual,
  votos[n_vot].HashAnterior: Cadena,
  n_vot: Entero
): Booleano;
Inicio
  var i, j: Entero;
  var es_valida = 1: Booleano;

  Para (i = 1 Hasta i = n_vot) Hacer;
    Para (j = 2 Hasta j = n_vot) Hacer;
      Si (votos[i].HashActual != votos[j].HashAnterior) Entonces;
        // La caden ha sido corrompida!!!
        es_valida = 0;
      Fin_Si
    Fin_Para
  Fin_Para

  Devolver(es_valida);
Fin_Funcion

Funcion validar_hash(texto, objetivo: Cadena): Booleano;
Inicio
  var coinciden = 1: Booleano;
  var comparacion: Cadena;

  // Creamos un hash a partir del texto que queremos comprobar
  comparacion = hash(texto);

  Si (comparacion != objetivo) Entonces;
    // Los hashes no coinciden
    coinciden = 0;
  Fin_Si

  Devolver(coinciden);
Fin_Funcion

Procedimiento cargar_candidatos(
  E/S:
  candidatos[n_presi].ID,
  candidatos[n_presi].Votos: Entero,
  candidatos[n_presi].Nombre,
  candidatos[n_presi].Partido: Cadena,
  E:
  n_presi: Entero,
  E/S:
  estado_eleccion: Entero
);
Inicio
  var i: Entero;

  Para (i = 1 Hasta i = n_presi) Hacer;
    candidatos[i].ID = i;
    candidatos[i].Votos = 0;
    Mostrar << "Ingrese el nombre de su candidato";
    Leer >> candidatos[i].Nombre;
    Mostrar << "Ingrese el partido de su candidato";
    Leer >> candidatos[i].Partido;
  Fin_Para

  estado_eleccion = 2;
Fin_Procedimiento  

Procedimiento mostrar_candidatos(
  E:
  Presi[n_presi].Nombre,
  Presi[n_presi].Partido: Cadena,
  Presi[n_presi].ID,
  n_presi: Entero,
);
Inicio
  Mostrar << "======= Lista de candidatos =========";

  Para (i = 1 Hasta i = n_presi) Hacer;
    Mostrar << "Id: ", Presi[i].ID;
    Mostrar << "Partido: ", Presi[i].Partido ;
    Mostrar << "Candidato: ", Presi[i].Nombre;
  Fin_Para
Fin_Procedimiento

Procedimiento resultados(
  E/S:
  candidatos[n_can].Votos: Entero,
  candidatos[n_can].Partido,
  candidatos[n_can].Nombre: Cadena,
  candidatosCopia[n_can].Votos: Entero,
  candidatosCopia[n_can].Partido,
  candidatosCopia[n_can].Nombre: Cadena,
  E:
  n_can, n_vot: Entero
);
Inicio
  var i, j: Entero;
  var aux1: Entero;
  var aux2: Cadena;
  var porcentaje: Real;

  Para (i = 1 Hasta i = n_can) Hacer;
    candidatosCopia[i].Votos = candidatos[i].Votos;
    candidatosCopia[i].Partido = candidatos[i].Partido;
    candidatosCopia[i].Nombre = candidatos[i].Nombre;
  Fin_Para

  Para (i = 1 Hasta i = n_can) Hacer;
    Para (j = 2 Hasta j = n_can - i) Hacer;
      Si (candidatosCopia[i].Votos > candidatosCopia[i].Votos) Entonces;
        aux1 = candidatosCopia[i].Votos;
        candidatosCopia[i].Votos = candidatosCopia[j].Votos;
        candidatosCopia[j].Votos = aux1;

        aux2 = candidatosCopia[i].Partido;
        candidatosCopia[i].Partido = candidatosCopia[j].Partido;
        candidatosCopia[j].Partido = aux2;

        aux2 = candidatosCopia[i].Nombre;
        candidatosCopia[i].Nombre = candidatosCopia[j].Nombre;
        candidatosCopia[j].Nombre = aux2;
      Fin_Si
    Fin_Para
  Fin_Para

  Para (i = 1 Hasta i = n_can) Hacer;
    porcentaje = (candidatosCopia[i].Votos / n_vot) * 100;
    Mostrar << "Posicion: ", i;
    Mostrar << "Candidato: ", candidatosCopia[i].Nombre;
    Mostrar << "Del partido: ", candidatosCopia[i].Partido;
    Mostrar << "Con un total de ", candidatosCopia[i].Votos, " votos";
    Mostrar << "Un ", porcentaje, "% de los votos";
  Fin_Para
Fin_Procedimiento

Funcion validar_resultados(
  candidatos[n_can].Votos: entero,
  candidatos[n_can].Partido,
  candidatos[n_can].Nombre: cadena,

  votos[n_vot].ID,
  votos[n_vot].Candidato,
  votos[n_vot].HashActual,
  votos[n_vot].HashAnterior: Cadena,

  n_can, n_vot: Entero
): Booleano;
Inicio
  var es_valida = 1: Booleano;
  var c_vot, objetivo: Entero;
  var i, j: Entero;
  var hash = "0";

  Para (i = 1 Hasta i = n_can) Hacer;
    objetivo = candidatos[i].Votos;
    c_vot = 0;

    Para (j = 1 Hasta j = n_vot) Hacer;
      Si (votos[j].Candidato = candidatos[i].Nombre) Entonces;
        c_vot = c_vot + 1;
      Fin_Si
    Fin_Para

    Si (c_vot != objetivo) Entonces;
      es_valida = 0;
    Fin_Si
  Fin_Para

  Para (i = 1 Hasta i = n_vot) Hacer;
    Para (j = 2 Hasta j = n_vot) Hacer;
      Si (votos[i].HashActual != votos[j].HashAnterior) Entonces;
        // La caden ha sido corrompida!!!
        es_valida = 0;
      Fin_Si
    Fin_Para
  Fin_Para

  Devolver(es_valida);
Fin_Funcion

Procedimiento Usuarios(
  E/S:
  N: cadena,
  A: cadena,
  fn: entero,
  mn: cadena,
  an: entero,
  ci: entero,
  Ed: entero,
  gn: cadena
);
Inicio
  var ob1: Entero;

  Mostrar<<" ingresar nombre del votante";
  Leer>> N;
  Mostrar<<" ingresar apellido del votante";
  Leer>> A;
  Mostar<<" ingresar fecha de nacimiento";
  Leer>> fn;

  Mientras (fn < 1 or fn > 31) hacer;
    Mostrar<<" error en los datos ingresados";
    Leer>> fn;
  Fin_Mientras

  Mostrar<<" ingresar mes de nacimiento";
  Mostrar<<"enero (1)  febrero (2)";
  Mostrar<<"marzo (3)  abril (4)";
  Mostrar<<"mayo (5)   junio (6)";
  Mostrar<<"julio (7)   agosto (8)";
  Mostrar<<"septiembre (9)  octubre (10)";
  Mostrar<<"noviembre (11)   diciembre (12)";
  Leer>> ob1;

  Mientras (ob1 < 1 or ob1 > 12) hacer,
    Mostrar<<" error en los datos ingresados";
    Leer>> ob1;
  Fin_Mientras 

  En_Caso (ob1 > 1) sea;
    Caso (ob1 = 1);
      mn = "enero";
    Caso (ob1 = 2);
      mn = "febrero";
    Caso (ob1 = 3);
      mn = "marzo";
    Caso (ob1 = 4);
      mn = "abril";
    Caso (ob1 = 5);
      mn = "mayo";
    Caso (ob1 = 6);
      mn = "junio",
    Caso (ob1 = 7);
      mn = "julio";
    Caso (ob1 = 8);
      mn = "agosto";
    Caso (ob1 = 9);
      mn = "septiembre";
    Caso (ob1 = 10);
      mn = "octubre";
    Caso (ob1 = 11);
      mn = "noviembre";
    Otro_Caso
      mn = "diciembre";
  Fin_Caso

  Mostrar<<" ingrese el año de nacimiento";
  Leer>> an;
  Mientras (an > 2007) hacer;
    Mostrar<<" error, no menores de edad";
    Leer >> an;
  Fin_mientras

  Ed = 2025 – an;
  Mostrar<<" ingresar cedula";
  Leer ci;

  Mientras (ci < 10000000) hacer;
    Mostrar<<"error",
    Leer>> ci;
  Fin_Mientras

  Mostrar<<" ingresar genero";
  Mostrar<<" hombre (1), Mujer (0)";
  Leer>> ob2;

  Si (ob2 = 1) entonces;
    gn = "hombre";
    sino
      gn = "mujer";
  Fin_si
Fin_Procedimiento

Procedimiento CifradoYFirma(E: Presi.Nombre: Cadena, Sys.LlavePublicaEleccion: Cadena, Usuario.LlavePrivada: Cadena, S: Tx.VotoCifrado, Tx.FirmaDigital: Cadena);
Inicio
  Tx.VotoCifrado = "CIFRADO_RSA_DE_" + Presi.Nombre;
  Tx.FirmaDigital = "FIRMA_DE_" + Usuario.LlavePrivada;

  Mostrar << "...Encriptando seleccion con llave..." << Sys.LlavePublicaEleccion;
  Mostrar << "...Firmando paquete digitalmente...";
Fin_Procedimiento


Procedimiento ConfigInicial(E/S: Sys.LlavePublicaEleccion: Cadena, Sys.EstadoLedger: Entero);
Inicio
  Sys.LlavePublicaEleccion = "*Inserte llave*";
  Sys.EstadoLedger = 1;
Fin_Procedimiento


Algoritmo ModuloEmisionVotos
  Registro: SistemaElectoral;
    LlavePublicaEleccion: Cadena;
    EstadoLedger: Entero;
  Fin_Registro

  Registro: Candidatos;
    Partido: Cadena;
    Nombre: Cadena;
    ID, Votos: Entero;
  Fin_Registro

  Registro: Votante;
    ID: Entero;
    HaVotado: Booleano;
    LlavePrivada: Cadena;
  Fin_Registro

  Registro: Transaccion;
    ID_Transaccion: Cadena;
    Timestamp: Cadena;
    VotoCifrado: Cadena;
    FirmaDigital: Cadena;
  Fin_Registro
Inicio
  Var SistemaElectoral: Sys;
  Var Candidatos: Presi[n_presi];
  Var Votante: Usuario[n_usuarios];
  Var Transaccion: Tx[n_usuarios];
  Var Opc, EstadoVoto, Confirmacion, Candidato1, Candidato2, Candidato3, Candidato4: Entero;

  var n_presi = 10, n_usuarios: Entero;

  cargar_candidatos(
    Presi[n_presi].Nombre,
    Presi[n_presi].Partido,
    Presi[n_presi].Votos,
    n_presi,
  );

  ConfigInicial(Sys.LlavePublicaEleccion, Sys.EstadoLedger);

  Mostrar << "--- SISTEMA DE VOTACION QUE MUESTRA LAS ACTAS ---";
  Mostrar << "Bienvenido al Modulo de Emision";

  Repetir
    Mostrar << "1. Emitir Voto";
    Mostrar << "2. Salir";
    Leer >> Opc;

    Mientras (Opc < 1 or Opc > 2) Hacer;
      Mostrar << "Error de Datos";
      Leer >> Opc;
    Fin_Mientras

    Si (Opc == 1) entonces;
      Mostrar << "Ingrese su ID de Votante:";
      Leer >> Usuario.ID;
      Mostrar << "Ingrese su Llave Privada:";
      Leer >> Usuario.LlavePrivada;

      VerificarUnicidad(Usuario.ID, Usuario.HaVotado, EstadoVoto);

      Si (EstadoVoto == 0) entonces;
        Mostrar << "Bienvenido Mano";
        Mostrar << "Elija al que se supone que le va a mejorar la vida"
        Mostrar << "1.Edmundo Gonsalez";
        Mostrar << "2.Elon Mak";
        Mostrar << "3.Nicolas Maldito Maduro";
        Mostrar << "4.Gabo Maps";
        Leer >> Candidato;

        En_Caso (Candidato > 0)Sea;
          Caso (Candidato = 1);
            Presi.Partido = "*Ingrese Partido*";
            Presi.Nombre = "Edmundo Gonzalez";
            Candidato1 = Cadidato1 + 1
            Presi.Voto = Candidato1;
          Caso (Candidato = 2)
            Presi.Partido = "*Ingrese Partido*";
            Presi.Nombre = "ElonMak";
            Candidato2 = Cadidato2 + 1
            Presi.Voto = Candidato2;
          Caso (Candidato = 3)
            Presi.Partido = "*Ingrese Partido*";
            Presi.Nombre = "Nicolas Maldito Maduro";
            Candidato3 = Cadidato3 + 1
            Presi.Voto = Candidato3;
          Caso (Candidato = 4)
            Presi.Partido = "*Ingrese Partido*";
            Presi.Nombre = "Gabo Maps";
            Candidato4 = Cadidato4 + 1
            Presi.Voto = Candidato4;
        Fin_Caso

       CifradoYFirma(Presi.Nombre, Sys.LlavePublicaEleccion, Usuario.LlavePrivada, Tx.VotoCifrado, Tx.FirmaDigital);
       GenerarTransaccion(Tx.ID_Transaccion, Tx.Timestamp);
       GuardarEnLedger(Tx.ID_Transaccion, Sys.EstadoLedger, Confirmacion);

      Si (Confirmacion == 1) entonces;
        Usuario.HaVotado = 1;
        ImpresionComprobante(Tx.ID_Transaccion, Tx.Timestamp, Tx.FirmaDigital);
      Sino;
        Mostrar << "Chamo no se que paso pero hubo un error bien feo.";
      Fin_Si

      Sino;
        Mostrar << "Epale chamo, mire usted ya voto.";
      Fin_Si
   Fin_Si

  Hasta (Opc == 2);
  Fin_Repetir
  Mostrar << "Que Dios te bendiga Mano";
Fin

Procedimiento GenerarTransaccion(E/S: Tx.ID_Transaccion, Tx.Timestamp: Cadena);
Inicio
  Tx.ID_Transaccion = "9923912";
  Tx.Timestamp = "2026-08-01 15:42:04";

  Mostrar << "...Estructurando datos...";
Fin_Procedimiento


Procedimiento GuardarEnLedger(E: Tx.ID_Transaccion: Cadena, Sys.EstadoLedger: Entero, S: Confirmacion: Entero);
Inicio
  Si (Sys.EstadoLedger == 1) entonces;
    Confirmacion = 1;
    Mostrar << "...Registrando en Ledger ID:..." << Tx.ID_Transaccion;
  Sino;
    Confirmacion = 0;
  Fin_Si
Fin_Procedimiento


Procedimiento ImpresionComprobante(E/S: Tx.ID_Transaccion, Tx.Timestamp, Tx.FirmaDigital: Cadena);
Inicio
  Mostrar << "==================================";
  Mostrar << "     COMPROBANTE DE VOTO         ";
  Mostrar << "==================================";
  Mostrar << "ID Transaccion:..." << Tx.ID_Transaccion;
  Mostrar << "Fecha y Hora:..." << Tx.Timestamp;
  Mostrar << "Firma Digital:..." << Tx.FirmaDigital;
  Mostrar << "Estado: VOTO REGISTRADO";
  Mostrar << "==================================";
Fin_Procedimiento

Procedimiento VerificarUnicidad(E: Usuario.ID: Cadena, Usuario.HaVotado: Entero, S: EstadoVoto: Entero);
Inicio
  Si (Usuario.HaVotado == 1) entonces;
    EstadoVoto = 1;

    Sino
      EstadoVoto = 0;
  Fin_Si
Fin_Procedimiento


```