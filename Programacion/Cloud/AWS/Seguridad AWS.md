# Seguridad

## Dominio seguridad y cumplimiento

conservar la integridad de los datos ante los robos o hackers es fundamental. 

## Pilares

saber como implementar para guardar los datos de nuestros clientes

* Modelo de responsabilidad compartida: 
* Principio de privilegio mínimo
* Pilar de la seguridad del marco bien diseñado 
* Servicios de seguridad 

## Seguridad en la nube

métodos y procedimientos que toma la empresa o entidad encargada para contrarrestar cualquier tipo de ataque a su plataforma. 

Tipos:
* Seguridad Física: dispositivos físicos que ofrecen algún tipo de seguridad como router, firewall, switch, etc . . (por parte del proveedor)
* Seguridad virtual: medidas que se toman ya en un entorno de software
	* Herramientas de monitoreo
	* Herramientas de tráfico de red
	* antivirus

## AWS seguridad en sus servicios

* Protección de datos
* Identity & Access management
* Protección de red y aplicación
* Detección de amenazas y monitoreo continuo
* Conformidad y privacidad de datos


## Seguridad compartida

Compromiso que depende del **proveedor** y del **cliente**. 


![seguridad compartida aws](./Shared_Responsibility_Model_V2.59.jpg)

Aws se encarga del mantenimiento de los recursos tecnológicos y físicos que este mismo ofrece. tanto seguridad física como de hardware. 

Cliente se encarga de las medidas que se toman en el software
* Herramientas de monitoreo
* Herramientas de tráfico de red
* antivirus


### Marco diseño

Marco bien diseñado es la estructura o arquitectura del servicio adquirido. 

pilares: 

* Excelencia operativa: capacidad para admitir el desarrollo y ejecutar cargas de trabajo de manera eficaz, obtener información acerca de las operaciones y mejorar continuamente admitiendo procesos y procedimientos para ofrecer valor del negocio
* seguridad: capacidad para proteger los datos, sistemas y activos, y aprovecha las tecnologías de la nube a fin de mejorar la seguridad
* fiabilidad: capacidad de una carga de trabajo para llevar a cabo la función prevista de forma correcta y consistente en el momento esperado. Incluye la capacidad de operar y probar la carga de trabajo a través de su ciclo de vida completo. Este documento
* eficiencia de rendimiento: utilizar recursos informáticos de umanera eficiente para cumplir con los requisitos del sistema y mantener esa eficiencia a medida que la demanda cambia y la tecnología evoluciona. 
* optimización de costos: ejecutar sistemas a fin de entregar valor de negocio al menor precio. 



	## Principio de privilegio mínimo 

	
Depende del proveedor y del cliente. Denominado PoLP a los permisos necesarios que tiene cada funcionario de una empresa para realizar su trabajo de manera correcta. 

**Access Management (IAM)** permite crear y administrar grupos y usuarios de AWS, además de administrar el acceso a los servicios y recursos del mismo de forma segura. Administra de forma segura los servicios y los recursos de la nube de AWS. 
* Administra grupos y usuarios
	* Tener permisos muy específicos
	* Acceso a través de la consola de administración
	* Adminstra roles para asignar permisos específicos por rol
* Administrar usuarios federados
	* Se utiliza para solucionar la gestión de identidades de los usuarios
	* Heredo del servicio local
* Provee permisos globales, es decir son validos en todas las regiones. 
* Proporciona acceso para usuarios de aws

**Administración de permisos** dar permisos pequeños y conceder más permisos cuando sea necesario. 

**Perfiles** elaborar políticas para que los usuarios realicen tareas especificas con los permisos necesarios. 

## Identity and access management

Beneficios

* Control granular
* Gestión de credenciales
* Seguridad mejorada
