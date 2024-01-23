# Usamos la imagen base oficial de Logstash
FROM docker.elastic.co/logstash/logstash:8.12.0

# Copiamos el pipeline de Logstash y el archivo CSV desde nuestro directorio local a la imagen
COPY ./pipelines/ /usr/share/logstash/pipeline/
COPY ./data/ /usr/share/logstash/data/
COPY ./config/pipelines.yaml /usr/share/logstash/config/pipelines.yml


# Exponemos el puerto que Logstash usará para la comunicación
EXPOSE 5044

# Ejecutamos Logstash con nuestro pipeline
CMD ["logstash"]
