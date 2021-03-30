# lab01- sumador 
laboratorio 01 introducción a HDL

En esta plantilla debe adicionar la documentación del laboratorio

* Juan Camilo Sierra Alean

Laboratorio de prueba.

Para iniciar se realizó la instalación de Quartus, luego se intalói también GitHub Desktop donde se realizó la clonación del laboratorio 1, este se editará desde esta aplicación.
Luego se entendieron los siguientes codigos:

1)
sum1bitcod
module sum1bcc_primitive (A, B, Ci,Cout,S);

  input  A;            /Se declarán las entradas y salidas del sumador    
  input  B;
  input  Ci;
  output Cout;
  output S;


  wire a_ab;            /Se declarán los 'Cables'
  wire x_ab;
  wire cout_t;

  and(a_ab,A,B);         /Se declarán compuertas según la tabla de verdad
  xor(x_ab,A,B);

  xor(S,x_ab,Ci);
  and(cout_t,x_ab,Ci);

  or (Cout,cout_t,a_ab);

endmodule

2)
module sum1bcc (A, B, Ci,Cout,S);

  input  A;              /Se declarán las entradas y salidas del sumador           
  input  B;                       
  input  Ci;
  output Cout;
  output S;

  reg [1:0] st;          /Almacenamiento de datos

  assign S = st[0];          /Se realiza la suma de los numeros y se asigna un valor a S y Cout
  assign Cout = st[1];

  always @ ( * ) begin
  	st  = 	A+B+Ci;
  end
  
endmodule

Luego de hacer esto observamos que la simulación muestre los valores esperados lo cual es así en este caso.





