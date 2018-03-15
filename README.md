# Katia_Flores_Fundamentos_ing_SW


<xproba>
 <arbol><nbarbol>ventas</nbarbol>
      <frecuencia>100</frecuencia>
 <dimension><nbdimension>tienda</nbdimension>

 <valor><nbvalor>aqui</nbvalor><frecuencia>80</frecuencia>
     <dimension><nbdimension>producto</nbdimension>
 
         <valor><encendido>0</encendido><nbvalor>TV</nbvalor><frecuencia>60</frecuencia></valor>

          <valor><encendido>1</encendido><nbvalor>RADIO</nbvalor><frecuencia>20</frecuencia></valor>
         
      </dimension>
  </valor>

 <valor><nbvalor>alla</nbvalor><frecuencia>20</frecuencia>
     <dimension><nbdimension>producto</nbdimension>
 
         <valor><valor><encendido>0</encendido><nbvalor>TV</nbvalor><frecuencia>15</frecuencia></valor>
          <valor><valor><encendido>0</encendido><nbvalor>SALA</nbvalor><frecuencia>5</frecuencia></valor>
      </dimension>
  </valor>

</dimension>      



________________________________________________________________________________________________

<?xml version="1.0" encoding="UTF-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
<xsl:template match="xproba">
    <xsl:for-each select="//valor">
    <xsl:if test="encendido='1'">
 probabilidad: <xsl:value-of select= "frecuencia div ../../frecuencia">


    </xsl:if>
    </xsl:for-each>

</xsl:template>
</xsl:stylesheet>


____________________________________________________________________________________________________
<xproba>
<arbol nbarbol="clientes" frecuencia='100'>
<atributo nbatributo="tienda">
<valor frecuencia='25' encendido="0" nbvalor="aquí">
<atributo nbatributo="producto">
<valor frecuencia='20' encendido="0" nbvalor="A"></valor>
<atributo nbatributo="modelo">
<valor frecuencia='15' encendido="1" nbvalor="Quemacocos"></valor>
<atributo nbatributo="color">
<valor frecuencia='10' encendido="0" nbvalor="Rojos"></valor>
<valor frecuencia='5' encendido="0" nbvalor="Negros"></valor>
</atributo>
</atributo>
<valor frecuencia='5' encendido="0" nbvalor="B" ></valor>
</atributo>
</valor>
<valor frecuencia='75' encendido="0" nbvalor="allá">
<atributo nbatributo="tienda">
<valor frecuencia='5' encendido="0" nbvalor="A"></valor>
<valor frecuencia='20' encendido="0" nbvalor="B"></valor>
<valor frecuencia='50' encendido="0" nbvalor="C"></valor>
</atributo>
</valor>
</atributo>
</arbol>
</xproba>

________________________________________________________________________________________________
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
<xsl:template match="//xproba/arbol">  <!--busca una etiqueta xproba y que tiene un hijo que se llama arbol-->
<xsl:for-each select="/descendant::valor">
   <xsl:value-of select="position()"/>
<!-- para todos los descendientes de árbol-->
  <xsl:if test="@encendido='1'"> 
<!-- verifica si está encendido --><br/>
   Posicion: <xsl:value-of select="position()"/>
   Nombre:<xsl:value-of select="@nbvalor"/>             
   Frecuencia:<xsl:value-of select="@frecuencia"/>
   Probabilidad:
<xsl:value-of select="@frecuencia div ../../../@frecuencia"/><br/>
  </xsl:if>
</xsl:for-each><br/>

</xsl:template>
</xsl:stylesheet>

___________________________________________________________________________________________________
<xloco>
    <usuario nbusuario="profe">
        <ontologia nbontologia="contador">
            <ideal nbideal="isan">
<atributos>
                    <atributo nbatributo="precio" tipo="decimal"/>
                    <atributo nbatributo="liminf" tipo="decimal"/>
                    <atributo nbatributo="limsup" tipo="decimal"/>
                    <atributo nbatributo="tasa" tipo="decimal"/>
                    <atributo nbatributo="fija" tipo="decimal"/>
                    <atributo nbatributo="isan" tipo="decimal"/>
 </atributos>
  <metodos>
                    <metodo nbmetodo="calcular_isan">
                        <asignacion>
                            <variable>precio</variable>
                            <operando>200000</operando>
                        </asignacion>
                        <decision>
                            <condicion>precio&amplt;75098.87</condicion>
                            <verdadero>
                                <metodo nbmetodo="es_nivel_1">
                                    <asignacion>
                                        <variable>tasa</variable>
                                        <operando>.02</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>fija</variable>
                                        <operando>0.00</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>liminferior</variable>
                                        <operando>0.01</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>limsuperior</variable>
                                        <operando>75098.87</operando>
                                    </asignacion>
                                </metodo>
                            </verdadero>
                            <falso>   
              <metodo nbmetodo="¿es_2?">
                  <decision>
                            <condicion>precio&amplt;90118.61)</condicion>
                            <verdadero>
                                <metodo nbmetodo="es_nivel_2">
                                    <asignacion>
                                        <variable>tasa</variable>
                                        <operando>.05</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>fija</variable>
                                        <operando>1501.96</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>liminferior</variable>
                                        <operando>75098.88</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>limsuperior</variable>
                                        <operando>90118.61</operando>
                                    </asignacion>
                                </metodo>
                            </verdadero>
                            <falso>    
       <metodo nbmetodo="¿es_3?">
                 <decision>
                            <condicion>precio&amplt;105138.43</condicion>
                            <verdadero>
                                <metodo nbmetodo="es_nivel_3">
                                    <asignacion>
                                        <variable>tasa</variable>
                                        <operando>.10</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>fija</variable>
                                        <operando>2252.97</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>liminferior</variable>
                                        <operando>98118.62</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>limsuperior</variable>
                                        <operando>105138.43</operando>
                                    </asignacion>
                                </metodo>
                            </verdadero>
     
                       <falso> 
      <metodo nbmetodo="¿es_4?">
                 <decision>
                            <condicion>precio&amplt;135117.89</condicion>
                            <verdadero>
                                <metodo nbmetodo="es_nivel_4">
                                    <asignacion>
                                        <variable>tasa</variable>
                                        <operando>.15</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>fija</variable>
                                        <operando>3754.94</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>liminferior</variable>
                                        <operando>105138.44</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>limsuperior</variable>
                                        <operando>135177.89</operando>
                                    </asignacion>
                                </metodo>
                            </verdadero>
     
                       <falso> 
                                <metodo nbmetodo="es_nivel_5">
                                    <asignacion>
                                        <variable>tasa</variable>
                                        <operando>0.17</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>fija</variable>
                                        <operando>8260.86</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>liminferior</variable>
                                        <operando>135177.90</operando>
                                    </asignacion>
                                    <asignacion>
                                        <variable>limsuperior</variable>
                                        <operando>135177.89</operando>
                                    </asignacion>
                       *             <asignacion>
                       *                 <variable>limsuperior</variable>
                       *                 <operando>135177.89</operando>
                       *             </asignacion>
                                </metodo>
                      </falso>
</decision>
</metodo>
</falso>
</decision>
</metodo>
</falso>
</decision>
</metodo>
</falso>
</decision>
</metodo>
</metodos>
</ideal>
</ontologia>
</usuario>
</xloco>
--------------------------------------------------------------------------------------------
<?xml version="1.0" encoding="UTF-8"?>
<xsl:stylesheet version="1.0"
xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

<xsl:template match="//ontologia">
  <xsl:apply-templates/>
</xsl:template>

<xsl:template match="ideal">
  <xsl:apply-templates select="atributos"/>
  <xsl:apply-templates select="metodos"/>
</xsl:template>

<xsl:template match="atributos"> 
  <xsl:apply-templates select="atributo"/>
</xsl:template>

<xsl:template match="atributo"> 
  " <xsl:value-of select="@nbatributo"/>": <br/>
  "<xsl:value-of select="@tipo"/>"
</xsl:template>

<xsl:template match="metodos">
 <xsl:apply-templates select="metodo"/>
</xsl:template>

<xsl:template match="metodo">
 "<xsl:value-of select="@nbmetodo"/>":function()<br/>    { <br/>
  <xsl:apply-templates select="asignacion"/>
  <xsl:apply-templates select="decision"/>
<br/>  return <xsl:value-of select="@nbmetodo"/>; <br/> }

 }

</xsl:template>

<xsl:template match="asignacion">
  <xsl:value-of select="variable"/> =
  <xsl:value-of select="operando"/>;<br/>
</xsl:template>

<xsl:template match="decision">
  if (<xsl:value-of select="condicion"/>)
  <xsl:apply-templates select="verdadero"/>
  <xsl:apply-templates select="falso"/>
</xsl:template>

<xsl:template match="verdadero">
  { <br/><xsl:apply-templates select="metodo"/> }
</xsl:template>

<xsl:template match="falso">
 else { <xsl:apply-templates select="metodo"/> }
</xsl:template>

</xsl:stylesheet>


------------------------------------------------------------------------------------------------------------

<!DOCTYPE html>
<html>
<body>

<h2>Convert a string into a function.</h2>

<p id="demo"></p>

<script>

var text = '{ "atributo":"nivel =  " , "calcular_isan":"function()              { precio=180000; if(precio<75098){ calcular_isan=1; }   else if   (precio<90118){calcular_isan=2;}   else if   (precio<105138){calcular_isan=3;}  else if (precio<135117){calcular_isan=4;}   else  {calcular_isan=5;} {return calcular_isan;}  }"                  ,"texto1":"tasa =  " , "var_tasa":"function()                                    { if(calcular_isan==1){var_tasa=.02;}  else if  (calcular_isan==2){var_tasa=.05;}  else if  (calcular_isan==3){var_tasa=.10;}    else if  (calcular_isan==4){var_tasa=.15;}   else if (calcular_isan==5){var_tasa=.17;}  {return var_tasa;}}"                                             ,"texto2":"fija  = ", "var_fija":"function()                                  { if(calcular_isan==1){var_fija=0.00;}  else if  (calcular_isan==2){var_fija=1501.96;}  else if  (calcular_isan==3){var_fija=2252.97;}       else if  (calcular_isan==4){var_fija=3754.94;}   else if (calcular_isan==5){var_fija=8260.86;}  {return var_fija;} }"                                   ,"texto3":"lim inferior =", "var_liminf":"function()                         { if(calcular_isan==1){var_liminf= 0.01;}  else if  (calcular_isan==2){var_liminf= 75098.88;}  else if  (calcular_isan==3){var_liminf=98118.62;}       else if  (calcular_isan==4){var_liminf=105138.44;}   else if (calcular_isan==5){var_liminf=135177.90;}  {return var_liminf;}}" ,"texto4":"lim superior =", "var_limsup":"function()                         { if(calcular_isan==1){var_limsup= 75098.87;}  else if  (calcular_isan==2){var_limsup= 90118.61;}  else if  (calcular_isan==3){var_limsup=105138.43;}       else if  (calcular_isan==4){var_limsup=135177.89;}   else if (calcular_isan==5){var_limsup=135177.89;}  {return var_limsup;} }"}';



var obj = JSON.parse(text);
obj.calcular_isan = eval("(" + obj.calcular_isan + ")");
obj.var_tasa= eval("(" + obj.var_tasa +")");
obj.var_fija= eval("(" + obj.var_fija +")");
obj.var_liminf= eval("(" + obj.var_liminf +")");
obj.var_limsup= eval("(" + obj.var_limsup +")");





document.getElementById("demo").innerHTML = obj.atributo   + obj.calcular_isan()+"  ,  " +obj.texto1 + obj.var_tasa() +"  ,  " +  obj.texto2+ obj.var_fija()+ "   ,  " +obj.texto3+ obj.var_liminf()+ "   ,  " +obj.texto4+ obj.var_limsup();

</script>

</body>
</html>
