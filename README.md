# lab01- sumador 
laboratorio 01 introducción a HDL

* Juan Camilo Sierra Alean

Laboratorio de prueba.

Para iniciar se realizó la instalación de Quartus, luego se intalói también GitHub Desktop donde se realizó la clonación del laboratorio 1, este se editará desde esta aplicación.
Luego se entendieron los siguientes codigos:

1)

![Imagen 1](https://github.com/unal-edigital1-lab/lab00-jusierraa/blob/master/sum1bitcod.JPG)
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
![Imagen 2](https://github.com/unal-edigital1-lab/lab00-jusierraa/blob/master/sum1bitcod.JPG)
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

Se realiza la simulación TestBench de cada sumador para verificar que todo este funcionando bien.
![Imagen 5](https://github.com/unal-edigital1-lab/lab00-jusierraa/blob/master/sum4bit_TBcod.JPG)

Luego de hacer esto observamos que la simulación muestre los valores esperados lo cual es así en este caso.

![Imagen 3](https://github.com/unal-edigital1-lab/lab00-jusierraa/blob/master/sum4bits.JPG)

![Imagen 4](https://github.com/unal-edigital1-lab/lab00-jusierraa/blob/master/sum4bits2.JPG)




 se realizan entonces diferentes cambios de nivel logico en cierto tiempo, con esto nos podemos cerciorar que cada sumador este funcionando bien, desde el sumador de 2 bits hasta el de 4 bits.
Ahora se procede a subir el codigo a la FPGA y comprobar que funciona


![Imagen 5](https://github.com/unal-edigital1-lab/lab00-jusierraa/blob/master/Sum4bitfpga2.JPG)

![Imagen 6](https://github.com/unal-edigital1-lab/lab00-jusierraa/blob/master/Sum4bitfpga1.JPG)


