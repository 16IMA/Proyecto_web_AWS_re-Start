# Guía AWS Practitioner - Practitioner Demo
Este proyecto es una aplicación web estática diseñada como recurso educativo para la certificación AWS Cloud Practitioner. El sitio presenta conceptos clave de AWS, como Amazon S3, de una manera visual y accesible.

## 🌐 Demo En Vivo
Puedes ver la web desplegada aquí: https://16ima.github.io/Proyecto_web_AWS_re-Start/

## 🛠️ Proceso de Desarrollo: De Stitch a Código Real
El flujo de trabajo seguido para este proyecto fue el siguiente:

- Diseño en Stitch: Se utilizó la herramienta de diseño de IA "Stitch" para prototipar la interfaz visual y la paleta de colores basada en la identidad de AWS.

- Extracción y Limpieza: El código generado se exportó a un archivo HTML base. Se realizó una limpieza profunda para eliminar estructura, imágenes y scripts innecesarios que no eran requeridas para este prototipo.

- Adaptación a Tailwind CSS: Se integró Tailwind CSS mediante su CDN para gestionar los estilos de forma ágil, permitiendo personalizar los colores de marca (aws-navy, aws-orange) directamente en el archivo.

- Optimización Estática: Se reemplazaron las rutas de imágenes externas por archivos locales y se configuraron enlaces externos (target="_blank") para recursos educativos y vídeos de YouTube.

## ☁️ Despliegue en Amazon S3
El sitio se aloja como una Static Website utilizando un bucket de Amazon S3 de manera temporal como ejercicio para el bootcamp re/Start AWS. A continuación, se detallan los pasos generales realizados:

1. Creación del Bucket
Se creó un bucket con un nombre único global (ej: static-web-practitioner).

Se seleccionó la región (us-west-2).

2. Configuración de Acceso Público
Se desactivó la opción "Block all public access" para permitir que los usuarios puedan ver la web.

Se añadió una Bucket Policy en formato JSON para otorgar permisos de lectura (s3:GetObject) a cualquier visitante:

JSON
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::static-web-practitioner/*"
        }
    ]
}
3. Habilitación de Static Website Hosting
En la pestaña de Properties, se activó "Static website hosting".

Se definió index.html como el documento de índice.

## 🚀 Tecnologías Utilizadas
HTML5 / CSS3

Tailwind CSS (Framework de estilos)

Google Material Symbols (Iconografía)

Amazon S3 (Hosting e infraestructura)
