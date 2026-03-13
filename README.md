# Lector de Patentes con Control de Acceso (Arduino)
Sistema inteligente de detección de patentes vehiculares utilizando Python, OpenCV y Tesseract OCR, integrado con Arduino para el control físico de barreras y una API REST para el registro en bitácora.

# Primeros pasos 
intes de comenzar, asegúrate de tener instalado:
1.-Python 3.x
2.-Tesseract OCR: Importante: Durante la instalación, anota la ruta (ej. C:\Program Files\Tesseract-OCR\tesseract.exe).
3.-Arduino IDE: Para verificar el puerto COM de tu placa.

### Instalación
1.- Instalar dependencias de Python:
pip install opencv-python numpy pytesseract requests pyserial

2. Configurar Tesseract: 
En el archivo detectarPatente.py, asegúrate de que la ruta coincida con tu instalación:
pytesseract.pytesseract.tesseract_cmd = 'C:\Tu\Ruta\A\tesseract.exe'

### Configuración de Hardware (Arduino)

1.-Conecta tu Arduino.
2.-Identifica el puerto COM en el IDE de Arduino (ej. COM4, COM6, COM7).
3.-Actualiza el puerto en los archivos correspondientes:
4.-Entrada: main_entrada.py -> ArduinoControl(port='COM4')
5.-Salida: main_salida.py -> ArduinoControl(port='COM6')


### Uso

Para iniciar el sistema de entrada: 
python main_entrada.py

Para iniciar el sistema de salida:
python main_salida.py

Nota: Presiona la tecla 'q' para cerrar las ventanas de video y finalizar los procesos.


### Notas de Implementación (Tips)
1.-Cámara: El sistema está configurado para resolución 1280x720. Si tu cámara no lo soporta, ajusta los valores en iniciar_camara.
2.-Detección: Se procesa 1 de cada 30 frames en la entrada para optimizar el uso de CPU.
3.-Formatos: El script es_patente_valida usa Regex para validar el formato de patente chilena (4 letras y 2 números).
