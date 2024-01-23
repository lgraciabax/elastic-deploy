# Usamos la imagen base oficial de Logstash
FROM docker.elastic.co/logstash/logstash:8.12.0

# Copiamos el pipeline de Logstash y el archivo CSV desde nuestro directorio local a la imagen
COPY ./pipelines/pipeline.conf /usr/share/logstash/pipeline/pipeline.conf
COPY ./data/users.csv /usr/share/logstash/data/users.csv

# Exponemos el puerto que Logstash usará para la comunicación
EXPOSE 5044

# Ejecutamos Logstash con nuestro pipeline
CMD ["logstash", "-f", "/usr/share/logstash/pipeline/*.conf"]
