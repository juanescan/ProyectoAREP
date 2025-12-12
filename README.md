# Proyecto AREP - Asistente de enfermería integrado con dispositivos IoT

Juan Esteban Cancelado


Samuel Alejandro Prieto


Juan José Díaz

## Configuración e Instrucciones de Uso

### Configuración Inicial

1. **Instalar todas las dependencias:**
```bash
pip install langchain langchain-openai langchain-community python-dotenv matplotlib plotly pandas reportlab
```

2. **Configurar API Key de OpenAI (opcional pero recomendado):**

Crear archivo `.env` en el directorio del proyecto:
```
OPENAI_API_KEY=tu_clave_api_aqui
```

### Componentes del Sistema

| Componente | Descripción | Funcionalidad Principal |
|------------|-------------|------------------------|
| **WearableAPI** | Simulador de dispositivo wearable | Genera datos de salud simulados |
| **HealthDatabase** | Base de datos SQLite | Almacena historial de mediciones |
| **HealthVisualizer** | Visualizador de datos | Crea gráficas y dashboards |
| **AgenteConversacional** | Agente de IA con memoria | Chat inteligente sobre salud |
| **SistemaNotificaciones** | Sistema de alertas | Detecta valores críticos |
| **GeneradorReportesPDF** | Exportador de reportes | Genera PDFs médicos |
| **SistemaSaludIntegrado** | Sistema completo | Integra todos los componentes |

### Uso Básico

**1. Inicializar el sistema:**
```python
# Sin OpenAI (funcionalidades básicas)
sistema = SistemaSaludIntegrado("user_12345")

# Con OpenAI (todas las funcionalidades)
sistema = SistemaSaludIntegrado("user_12345", api_key=os.getenv('OPENAI_API_KEY'))
```

**2. Ver resumen del estado:**
```python
sistema.resumen_estado()
```

**3. Ejecutar monitoreo continuo:**
```python
sistema.monitoreo_continuo(intervalo_segundos=60, duracion_minutos=10)
```

**4. Generar dashboard visual:**
```python
sistema.mostrar_dashboard()
```

**5. Exportar reporte PDF:**
```python
sistema.generar_reporte_completo()
```

**6. Chatear con el agente de IA:**
```python
respuesta = sistema.chat_con_agente("¿Cómo está mi presión arterial?")
print(respuesta)
```

### Integración con Dispositivos Reales

Para conectar con APIs reales de wearables:

**Fitbit:**
```python
# Requiere OAuth 2.0
import fitbit
auth = fitbit.Fitbit(client_id, client_secret, access_token=token)
heart_rate = auth.intraday_time_series('activities/heart', detail_level='1min')
```

**Apple Health:**
```python
# Usar HealthKit en iOS
# Exportar datos a JSON/XML
```

**Garmin:**
```python
# Usar Garmin Health API
# Requiere registro de desarrollador
```

### Próximas Mejoras

- 🔄 Sincronización automática con dispositivos reales
- 📱 Aplicación móvil con React Native
- 🌐 API REST para acceso remoto
- 🔐 Autenticación de usuarios
- 📧 Notificaciones por email/SMS
- 🧠 Modelos de ML para predicción de anomalías
- 📊 Analytics avanzado con tendencias
- 👥 Panel para médicos/profesionales

### Soporte y Documentación

- **LangChain:** https://python.langchain.com/
- **OpenAI API:** https://platform.openai.com/docs
- **Plotly:** https://plotly.com/python/
- **ReportLab:** https://www.reportlab.com/docs/reportlab-userguide.pdf