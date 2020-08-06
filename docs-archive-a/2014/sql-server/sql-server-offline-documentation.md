---
title: Documentos sin conexión para SQL Server 2014
description: Obtenga información sobre cómo instalar la documentación sin conexión para SQL Server 2014. Utilice SQL Server Management Studio (SSMS) para ver el contenido sin conexión.
ms.prod: sql
ms.technology: install
ms.topic: conceptual
ms.assetid: 51f8a08c-51d0-41d8-8bc5-1cb4d42622fb
author: markingmyname
ms.author: maghan
ms.reviewer: carlrab
ms.date: 07/19/2020
ms.openlocfilehash: bfd4adc658a203f8e2d22ef77ce0381084e36363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672367"
---
# <a name="install-sql-server-2014-offline-documentation"></a>Instalación de la documentación sin conexión de SQL Server 2014

En este artículo se describe cómo descargar y ver el contenido de SQL Server 2014 sin conexión. El contenido sin conexión le permite acceder a la documentación sin conexión a Internet (aunque se necesita una conexión a Internet para descargarla).

La técnica implica el uso del menú **ayuda** de SQL Server Management Studio (SSMS) para tener acceso a la utilidad del visor de ayuda (HlpViewer.exe).

La documentación sin conexión está disponible para las versiones de SQL Server en el intervalo de 2012-2019 y quizás también para versiones posteriores. Aunque puede ver el contenido de las [versiones anteriores en línea](https://docs.microsoft.com/previous-versions/sql/), una opción sin conexión proporciona una manera cómoda de acceder al contenido anterior.

- [SQL Server 2014](#sql-server-2014-offline-content)
- [SQL Server 2012](#sql-server-2012-offline-content)

Para SQL Server 2016 y versiones posteriores, consulte su documentación específica de la versión para obtener información sobre cómo esas versiones controlan su documentación sin conexión.

## <a name="sql-server-2014-offline-content"></a>Contenido sin conexión de SQL Server 2014

> [!IMPORTANT]
> El contenido de Transact-SQL de SQL 2014 solo está disponible sin conexión.

Con los siguientes pasos se explica cómo cargar contenido sin conexión en SQL Server 2014.

1. Descargue el contenido de la [Documentación del producto de Microsoft SQL Server 2014 para los entornos restringidos de firewall y proxy](https://www.microsoft.com/download/details.aspx?id=42557) del centro de descarga y guárdelo en una carpeta.

2. Descomprima el archivo para ver el archivo *. MSHA* .

   ![Archivo de instalación de la documentación de Ayuda de SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. En SSMS, seleccione **Agregar y quitar contenido de la Ayuda** en el menú Ayuda.

   ![Agregar y quitar contenido en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   El Visor de Ayuda se abre en la pestaña Administrar contenido.

4. Para instalar el último contenido de Ayuda, seleccione **Disco** en Origen de la instalación y, después, haga clic en los puntos suspensivos (...).

   ![Origen del disco de Administrar contenido en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > En Ruta de acceso del almacén local de la pestaña Administrar contenido, se muestra dónde se encuentra el contenido en el equipo local. Para cambiar la ubicación, seleccione **Mover**, especifique otra ruta de carpeta en el campo **A** y, después, seleccione **Aceptar**.
   Si se produce un error en la instalación de la Ayuda después de cambiar la ruta de acceso del almacén local, cierre y vuelva a abrir el Visor de ayuda. Compruebe que la nueva ubicación aparece en la ruta de acceso del almacén local y vuelva a intentar realizar la instalación.

5. Encuentre la carpeta donde se descomprimió el contenido. Seleccione el archivo **HelpContentSetup.msha** en la carpeta y, después, seleccione **Abrir**.

   ![Abrir el archivo Setup.msha del contenido de Ayuda de SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. Escriba *sql server 2014* en la barra de búsqueda. Una vez que vea el contenido disponible de 2014, seleccione **Agregar** junto a cada paquete de contenido (libro) que desee instalar en el Visor de Ayuda y, a continuación, seleccione **Actualizar**.

   ![Búsqueda de libros de SQL Server 2014 en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Libros de SQL Server 2014 sobre adición y actualización en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > Si el visor de ayuda se bloquea (se bloquea) mientras agrega contenido, cambie la línea de la caché de LastRefreshed = " \<mm/dd/yyyy> 00:00:00" en el archivo%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings o HlpViewer_VisualStudiox_en-US. Settings en una fecha futura. Para obtener más información sobre este problema, vea [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio)(El Visor de Ayuda de Visual Studio se bloquea).

7. Puede comprobar si el contenido de SQL Server 2014 está instalado; para ello, busque *sql server 2014* en el panel de contenido de la izquierda.

   ![Libros de SQL Server 2014 actualizados automáticamente](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a>Contenido sin conexión de SQL Server 2012

Con los siguientes pasos se explica cómo cargar contenido sin conexión en SQL Server 2012.

1. Descargue el contenido de la [Documentación del producto de Microsoft SQL Server 2012 para los entornos restringidos de firewall y proxy](https://www.microsoft.com/download/details.aspx?id=35750) del centro de descarga y guárdelo en una carpeta.

2. Descomprima el archivo para ver el archivo *. MSHA* .

   ![Archivo de instalación del contenido de Ayuda de SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. En SSMS, seleccione **Agregar y quitar contenido de la Ayuda** en el menú Ayuda.

   ![Agregar y quitar contenido en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   El Visor de Ayuda se abre en la pestaña Administrar contenido.

4. Para instalar el último contenido de Ayuda, seleccione **Disco** en Origen de la instalación y, después, haga clic en los puntos suspensivos (...).

   ![Origen del disco de Administrar contenido en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > En Ruta de acceso del almacén local de la pestaña Administrar contenido, se muestra dónde se encuentra el contenido en el equipo local. Para cambiar la ubicación, seleccione **Mover**, especifique otra ruta de carpeta en el campo **A** y, después, seleccione **Aceptar**.
   Si se produce un error en la instalación de la Ayuda después de cambiar la ruta de acceso del almacén local, cierre y vuelva a abrir el Visor de ayuda. Compruebe que la nueva ubicación aparece en la ruta de acceso del almacén local y vuelva a intentar realizar la instalación.

5. Encuentre la carpeta donde se descomprimió el contenido. Seleccione el archivo **HelpContentSetup.msha** en la carpeta y, después, seleccione **Abrir**.

   ![Abrir el archivo Setup.msha del contenido de Ayuda de SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. Escriba *sql server 2012* en la barra de búsqueda. Una vez que vea el contenido disponible de 2012, seleccione **Agregar** junto a cada paquete de contenido (libro) que desee instalar en el Visor de Ayuda y, a continuación, seleccione **Actualizar**.

   ![Búsqueda de libros de SQL Server 2012 en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Libros de SQL Server 2012 sobre adición y actualización en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > Si el visor de ayuda se bloquea (se bloquea) mientras agrega contenido, cambie la línea de la caché de LastRefreshed = " \<mm/dd/yyyy> 00:00:00" en el archivo%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings o HlpViewer_VisualStudiox_en-US. Settings en una fecha futura. Para obtener más información sobre este problema, vea [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio)(El Visor de Ayuda de Visual Studio se bloquea).

7. Puede comprobar si el contenido de SQL Server 2012 está cargado; para ello, busque *sql server 2012* en el panel de contenido de la izquierda.

   ![Documentación de SQL Server 2012 actualizada automáticamente](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a>Visualización de la documentación sin conexión

Puede ver SQL Server contenido de la ayuda mediante el menú **ayuda** de la versión más reciente de SQL Server Management Studio (SSMS).

### <a name="view-offline-help-content-in-ssms"></a>Visualización del contenido de la Ayuda sin conexión en SSMS

Para ver la Ayuda instalada en SSMS, seleccione **Iniciar en el Visor de Ayuda** en el menú Ayuda para iniciar el Visor de Ayuda.

   ![Iniciar en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

Este se abrirá en la pestaña Administrar contenido, con la tabla de contenido de la Ayuda instalada en el panel izquierdo. Seleccione los artículos de la tabla de contenido para que se muestren en el panel de la derecha.

> [!Important]
> Si el panel de contenido no está visible, seleccione Contenido en el margen izquierdo. Seleccione el icono de marcador para mantener abierto el panel de contenido.  

   ![Visor de Ayuda con contenido](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)
