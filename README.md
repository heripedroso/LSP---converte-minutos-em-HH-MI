# LSP---Converte-minutos-em-HH-MM
Função helper que converte número de minutos em uma string no formato HH:MI

----
Para usar a função na regra, deve-se declará-la no início da mesma.
É interessante que se reserve, por exemplo, a regra 001 apenas para implementar funções.
Em implementações de relatório, tenho o hábito de implementar as funções em Funções Globais no Modelo Gerador.

```
@==============================================================================@
Definir Funcao converteMinutosEmHHMI(Numero nMinutos);
Definir Alfa aHorasMinutos;  @ Variável de saída. @

Funcao converteMinutosEmHHMI(Numero nMinutos);
{ 
     horas = 0;
     Se ( nMinutos > 0)
     {
           Enquanto (nMinutos >= 60)
           {
                 nMinutos = nMinutos-60; 
                 horas = horas + 1;
           }
           Se (horas >= 10)
                 aHorasMinutos = aHorasMinutos + "" +formatar(horas,"%2.0f"); 
           senao
                 aHorasMinutos = aHorasMinutos + "0"+formatar(horas,"%1.0f"); 
           Se (nMinutos >= 10)
                 aHorasMinutos = aHorasMinutos + ":" +formatar(nMinutos,"%2.0f");
           senao
                 aHorasMinutos = aHorasMinutos + ":0"+formatar(nMinutos,"%1.0f");
     }
     Senao
     {
           aHorasMinutos = "00:00";
     }
};
@==============================================================================@
```
