Esqueleto para comezar un proxecto con bind9

1. Instala o servidor BIND9 no equipo darthvader. Comproba que xa funciona coma servidor DNS caché pegando no documento de entrega a saída deste comando dig @localhost www.edu.xunta.es

    ![image1](imagenes/image1.png)

2. Configura o servidor BIND9 para que empregue como reenviador 8.8.8.8. pegando no documento de entrega contido do ficheiro /etc/bind/named.conf.options e a saída deste comando: dig @localhost www.mecd.gob.es 

    - named.conf.options:

    ![image2](imagenes/image2.png)

    $ dig @localhost www.mecd.gob.es:

    ![image3](imagenes/image3.png)

3. Instala unha zona primaria de resolución directa chamada "starwars.lan" e engade os seguintes rexistros de recursos (a maiores dos rexistros NS e SOA imprescindibles):

    - archivo ./named.conf.local:

    ![image4](imagenes/image4.png)

    - archivo ./db.20.168.192:

    ![image5](imagenes/image5.png)



4. Instala unha zona de resolución inversa que teña que ver co enderezo do equipo darthvader, e engade rexistros PTR para os rexistros tipo A do exercicio anterior. Pega no documento de entrega o contido do arquivo de zona, e do arquivo /etc/bind/named.conf.local

    - archivo ./db.starwars.lan:

    ![image6](imagenes/image6.png)

    - archivo ./named.conf.local:

    ![image7](imagenes/image7.png)

5. Comproba que podes resolver os distintos rexistros de recursos. Pega no documento de entrega a saída dos comandos:

    - $nslookup darthvader.starwars.lan. localhost:

    ![image8](imagenes/image8.png)

    - $nslookup skywalker.starwars.lan localhost

    ![image9](imagenes/image9.png)

    - $nslookup starwars.lan localhost

    ![image10](imagenes/image10.png)

    - $nslookup -q=mx starwars.lan localhost

    ![image11](imagenes/image11.png)

    - $nslookup -q=ns starwars.lan localhost

    ![image12](imagenes/image12.png)

    - $nslookup -q=soa starwars.lan localhost

    ![image13](imagenes/image13.png)

    - $nslookup -q=txt lenda.starwars.lan localhost
    
    ![image14](imagenes/image14.png)

    - $nslookup 192.168.20.11 localhost

    ![image15](imagenes/image15.png)

