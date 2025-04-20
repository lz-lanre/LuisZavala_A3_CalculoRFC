/*luis Zavala - Actividad 3*/

/*bibliotecas requeridas*/
#include <iostream>
#include <string>
#include <cctype>

int main()
{
/*declaracion de variables a utilizar (string - cadena de caracteres)*/
    std::string nombre,apellido1,apellido2,fechanacimiento,v1,v2,v3,v4,rfc1,dia,mes,anio,RFC;
/*solicitud de datos requeridos, lectura y asignacion a sus respectivas variables*/
    std::cout <<"Ingresa tu nombre: ";
    std::getline(std::cin,nombre);
    std::cout<<"Ingresa tu aprimer apellido: ";
    std::getline(std::cin,apellido1);
    std::cout<<"Ingresa tu segundo apellido (En caso de no contar, presiona ENTER): ";
    std::getline(std::cin,apellido2);
/*en el caso del 2do apellido, hay la opcion de que no exista, por lo que se usa una condicional e IF para asignar un valor 'x' en dado caso*/
    if(apellido2=="") /*aqui pregunta si el apellido 2 esta en blanco (le dio enter)*/
    {
        apellido2="x";
    }
    std::cout<<"Ingresa tu fecha de nacimiento (formato DD/MM/AAAA): ";
    std:getline(std::cin,fechanacimiento);
/*se asigna el valor del primer digito del rfc del primer caracter de la variable asignada al 1er apellido*/
    v1=apellido1[0];
/*para el valor del 2do digito se requiere un ciclo en el que se compare cada caracter del 1er apellido contra las vocales*/
/*como no se sabe si el usuario escribira en mayusculas o minusculas, se consideran ambas opciones*/
/*en el primer acierto se cierra ciclo, si no hay aciertos asigna valor 'x'*/
    for(int i=1; i<apellido1.length();++i) /*el ciclo dura desde desde i=1 hasta el tamaño del apellido 1*/
    {
        char c=apellido1[i];/*inicialmente se le asigna a 'c' el valor del 2do caracter en el apellido*/
        if (c=='A'||c=='E'||c=='I'||c=='O'||c=='U'||c=='a'||c=='e'||c=='i'||c=='o'||c=='u') /*'c' lo compara contra todas las vocales*/
        {
            v2=apellido1[i]; /*si 'c' es igual a una de las vocales, cierra el ciclo, si no se repite e 'i' aumenta en 1*/
            break;
        }
        else v2='x'; /*si no encontro ninguna vocal, asigna 'x'*/
    }
/*asignacion de 3er valor tomando el primer caracter de la variable asignada al 2do apellido*/
    v3=apellido2[0];
/*asignacion de 4to valor tomando el primer caracter de la variable asignada al nombre*/
    v4=nombre[0];
/*como se requiere tener la opcion de que si los primeros 4 digitos forman una palabra vulgar se cambie el valor del 4to digito*/
/*primero asigno los 4 digitos individuales a una sola variable*/
    rfc1=(v1+""+v2+""+v3+""+v4);
/*como no se si el usuario escribira en mayusculas o minusculas, se cambia todo a mayusculas*/
/*para el cambio, se requiere un ciclo de 4 iteraciones, que cambie caracter por caracter a mayusculas*/
/*NOTA: por alguna razon al querer hacerlo directo con toda la palabra no me lo permitio*/
    for (int m=0;m<4;++m)
    {
        rfc1[m]=toupper(rfc1[m]);
    }
/*ya con la variable concatenada en mayuscula, sera comparada contra diferentes vulgaridades*/
/*si alguna da positivo, cambiara el 4to digito de la variable concatenada a 'x'*/
    if(rfc1=="PUTA"||rfc1=="PUTO"||rfc1=="CULO"||rfc1=="JOTO"||rfc1=="JOTA"||rfc1=="PENE"||rfc1=="SEXO")
    {
        rfc1[3]='X';
    }
/*asignacion de valores a las variables de dia, mes y año. se substraen de la fecha total dada por el usuario*/
/*espero que utilice el formato de fecha solicitado porque si no, no da*/
    dia=fechanacimiento.substr(0,2);
    mes=fechanacimiento.substr(3,2);
    anio=fechanacimiento.substr(8,2);
/*se juntan todos los digitos para formar el RFC, la parte de la homoclave se simulara con un 'XXX'*/
    RFC=(rfc1+""+anio+""+mes+""+dia+"XXX");
/*se imprime el valor final de RFC*/
    std::cout<<"Tu RFC sin homoclave es: "<<RFC;
    return 0;
}
