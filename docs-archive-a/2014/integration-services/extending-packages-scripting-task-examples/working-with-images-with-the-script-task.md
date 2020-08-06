---
title: Trabajar con imágenes con la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- graphics [Integration Services]
- Script task [Integration Services], images
- Drawing namespace
- images [Integration Services]
- SSIS Script task, images
- Script task [Integration Services], examples
- thumbnails [Integration Services]
- System.Drawing namespace
- JPEG format [Integration Services]
- .jpeg files
ms.assetid: 74aeb7ab-51b2-4b9f-84ee-0b46a7908ab9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75a5b72f87a4463d7270dc9f28529a81525860cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673200"
---
# <a name="working-with-images-with-the-script-task"></a><span data-ttu-id="fcade-102">Trabajar con imágenes con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="fcade-102">Working with Images with the Script Task</span></span>
  <span data-ttu-id="fcade-103">Una base de datos de productos o usuarios suele incluir imágenes además de datos de texto y numéricos.</span><span class="sxs-lookup"><span data-stu-id="fcade-103">A database of products or users frequently includes images in addition to text and numeric data.</span></span> <span data-ttu-id="fcade-104">El espacio de nombres `System.Drawing` de Microsoft .NET Framework proporciona clases para manipular las imágenes.</span><span class="sxs-lookup"><span data-stu-id="fcade-104">The `System.Drawing` namespace in the Microsoft .NET Framework provides classes for manipulating images.</span></span>  
  
 [<span data-ttu-id="fcade-105">Ejemplo 1: Convertir las imágenes al formato JPEG</span><span class="sxs-lookup"><span data-stu-id="fcade-105">Example 1: Convert Images to JPEG Format</span></span>](#example1)  
  
 [<span data-ttu-id="fcade-106">Ejemplo 2: Crear y guardar las imágenes en miniatura</span><span class="sxs-lookup"><span data-stu-id="fcade-106">Example 2: Create and Save Thumbnail Images</span></span>](#example2)  
  
> [!NOTE]  
>  <span data-ttu-id="fcade-107">Si desea crear una tarea que pueda reutilizar más fácilmente en varios paquetes, considere la posibilidad de utilizar el código de este ejemplo de tarea Script como punto inicial de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="fcade-107">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="fcade-108">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="fcade-108">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
##  <a name="example-1-description-convert-images-to-jpeg-format"></a><a name="example1"></a> <span data-ttu-id="fcade-109">Ejemplo 1: Descripción: convertir las imágenes al formato JPEG</span><span class="sxs-lookup"><span data-stu-id="fcade-109">Example 1 Description: Convert Images to JPEG Format</span></span>  
 <span data-ttu-id="fcade-110">En el ejemplo siguiente se abre un archivo de imagen especificado por una variable y se guarda como un archivo JPEG comprimido mediante un codificador.</span><span class="sxs-lookup"><span data-stu-id="fcade-110">The following example opens an image file specified by a variable and saves it as a compressed JPEG file by using an encoder.</span></span> <span data-ttu-id="fcade-111">El código para recuperar la información del codificador se encapsula en una función privada.</span><span class="sxs-lookup"><span data-stu-id="fcade-111">The code to retrieve encoder information is encapsulated in a private function.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-a-single-image-file"></a><span data-ttu-id="fcade-112">Para configurar este ejemplo de la tarea Script para su uso con un archivo de imagen único</span><span class="sxs-lookup"><span data-stu-id="fcade-112">To configure this Script Task example for use with a single image file</span></span>  
  
1.  <span data-ttu-id="fcade-113">Cree una variable de cadena denominada `CurrentImageFile` y establezca el valor en la ruta de acceso y nombre de un archivo de imagen existente.</span><span class="sxs-lookup"><span data-stu-id="fcade-113">Create a string variable named `CurrentImageFile` and set its value to the path and file name of an existing image file.</span></span>  
  
2.  <span data-ttu-id="fcade-114">En la página **script** del editor de la **tarea script**, agregue la `CurrentImageFile` variable a la `ReadOnlyVariables` propiedad.</span><span class="sxs-lookup"><span data-stu-id="fcade-114">On the **Script** page of the **Script Task Editor**, add the `CurrentImageFile` variable to the `ReadOnlyVariables` property.</span></span>  
  
3.  <span data-ttu-id="fcade-115">En el proyecto de script, establezca una referencia al espacio de nombres `System.Drawing`.</span><span class="sxs-lookup"><span data-stu-id="fcade-115">In the script project, set a reference to the `System.Drawing` namespace.</span></span>  
  
4.  <span data-ttu-id="fcade-116">En el código, utilice las instrucciones `Imports` para importar los espacios de nombres `System.Drawing` y `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="fcade-116">In your code, use `Imports` statements to import the `System.Drawing` and `System.IO` namespaces.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-multiple-image-files"></a><span data-ttu-id="fcade-117">Para configurar este ejemplo de la tarea Script para su uso con varios archivos de imagen</span><span class="sxs-lookup"><span data-stu-id="fcade-117">To configure this Script Task example for use with multiple image files</span></span>  
  
1.  <span data-ttu-id="fcade-118">Coloque la tarea Script dentro de un contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="fcade-118">Place the Script task within a Foreach Loop container.</span></span>  
  
2.  <span data-ttu-id="fcade-119">En la página **Colección** del **Editor de bucles Para cada uno**, seleccione como enumerador el **Enumerador de archivos Para cada uno** y especifique la ruta de acceso y la máscara de archivo de los archivos de código fuente, como "\*.bmp".</span><span class="sxs-lookup"><span data-stu-id="fcade-119">On the **Collection** page of the **Foreach Loop Editor**, select the **Foreach File Enumerator** as the enumerator, and specify the path and file mask of the source files, such as "\*.bmp."</span></span>  
  
3.  <span data-ttu-id="fcade-120">En la página **Asignaciones de variables**, asigne la variable `CurrentImageFile` al índice 0.</span><span class="sxs-lookup"><span data-stu-id="fcade-120">On the **Variable Mappings** page, map the `CurrentImageFile` variable to Index 0.</span></span> <span data-ttu-id="fcade-121">Esta variable pasa el nombre de archivo actual a la tarea Script de cada iteración del enumerador.</span><span class="sxs-lookup"><span data-stu-id="fcade-121">This variable passes the current file name to the Script task on each iteration of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcade-122">Estos pasos son adicionales a los enumerados en el procedimiento para el uso con un archivo de imagen único.</span><span class="sxs-lookup"><span data-stu-id="fcade-122">These steps are in addition to the steps listed in the procedure for use with a single image file.</span></span>  
  
### <a name="example-1-code"></a><span data-ttu-id="fcade-123">Código de ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="fcade-123">Example 1 Code</span></span>  
  
```vb  
Public Sub Main()  
  
    'Create and initialize variables.  
    Dim currentFile As String  
    Dim newFile As String  
    Dim bmp As Bitmap  
    Dim eps As New Imaging.EncoderParameters(1)  
    Dim ici As Imaging.ImageCodecInfo  
    Dim supportedExtensions() As String = _  
        {".BMP", ".GIF", ".JPG", ".JPEG", ".EXIF", ".PNG", _  
        ".TIFF", ".TIF", ".ICO", ".ICON"}  
  
    Try  
        'Store the variable in a string for local manipulation.  
        currentFile = Dts.Variables("CurrentImageFile").Value.ToString  
        'Check the extension of the file against a list of  
        'files that the Bitmap class supports.  
        If Array.IndexOf(supportedExtensions, _  
            Path.GetExtension(currentFile).ToUpper) > -1 Then  
  
            'Load the file.  
            bmp = New Bitmap(currentFile)  
  
            'Calculate the new name for the compressed image.  
            'Note: This will overwrite existing JPEGs.  
            newFile = Path.Combine( _  
                Path.GetDirectoryName(currentFile), _  
                String.Concat(Path.GetFileNameWithoutExtension(currentFile), _  
                ".jpg"))  
  
            'Specify the compression ratio (0=worst quality, 100=best quality).  
            eps.Param(0) = New Imaging.EncoderParameter( _  
                Imaging.Encoder.Quality, 75)  
  
            'Retrieve the ImageCodecInfo associated with the jpeg format.  
            ici = GetEncoderInfo("image/jpeg")  
  
            'Save the file, compressing it into the jpeg encoding.  
            bmp.Save(newFile, ici, eps)  
        Else  
            'The file is not supported by the Bitmap class.  
            Dts.Events.FireWarning(0, "Image Resampling Sample", _  
                "File " & currentFile & " is not a supported format.", _  
                "", 0)  
         End If  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        'An error occurred.  
        Dts.Events.FireError(0, "Image Resampling Sample", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
  
Private Function GetEncoderInfo(ByVal mimeType As String) As Imaging.ImageCodecInfo  
  
    'The available image codecs are returned as an array,  
    'which requires code to iterate until the specified codec is found.  
  
    Dim count As Integer  
    Dim encoders() As Imaging.ImageCodecInfo  
  
    encoders = Imaging.ImageCodecInfo.GetImageEncoders()  
  
    For count = 0 To encoders.Length  
        If encoders(count).MimeType = mimeType Then  
            Return encoders(count)  
        End If  
    Next  
  
    'This point is only reached if a codec is not found.  
    Err.Raise(513, "Image Resampling Sample", String.Format( _  
        "The {0} codec is not available. Unable to compress file.", _  
            mimeType))  
    Return Nothing  
  
End Function  
  
```  
  
##  <a name="example-2-description-create-and-save-thumbnail-images"></a><a name="example2"></a> <span data-ttu-id="fcade-124">Ejemplo 2: Descripción: crear y guardar las imágenes en miniatura</span><span class="sxs-lookup"><span data-stu-id="fcade-124">Example 2 Description: Create and Save Thumbnail Images</span></span>  
 <span data-ttu-id="fcade-125">En el ejemplo siguiente se abre un archivo de imagen especificado por una variable, se crea una miniatura de la imagen a la vez que se mantiene una relación de aspecto constante y se guarda la miniatura con un nombre de archivo modificado.</span><span class="sxs-lookup"><span data-stu-id="fcade-125">The following example opens an image file specified by a variable, creates a thumbnail of the image while maintaining a constant aspect ratio, and saves the thumbnail with a modified file name.</span></span> <span data-ttu-id="fcade-126">El código que calcula el alto y ancho de la miniatura a la vez que mantiene una relación de aspecto constante se encapsula en una subrutina privada.</span><span class="sxs-lookup"><span data-stu-id="fcade-126">The code that calculates the height and width of the thumbnail while maintaining a constant aspect ratio is encapsulated in a private subroutine.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-a-single-image-file"></a><span data-ttu-id="fcade-127">Para configurar este ejemplo de la tarea Script para su uso con un archivo de imagen único</span><span class="sxs-lookup"><span data-stu-id="fcade-127">To configure this Script Task example for use with a single image file</span></span>  
  
1.  <span data-ttu-id="fcade-128">Cree una variable de cadena denominada `CurrentImageFile` y establezca el valor en la ruta de acceso y nombre de un archivo de imagen existente.</span><span class="sxs-lookup"><span data-stu-id="fcade-128">Create a string variable named `CurrentImageFile` and set its value to the path and file name of an existing image file.</span></span>  
  
2.  <span data-ttu-id="fcade-129">Cree también la variable entera `MaxThumbSize` y asígnela un valor en píxeles, como 100.</span><span class="sxs-lookup"><span data-stu-id="fcade-129">Also create the `MaxThumbSize` integer variable and assign a value in pixels, such as 100.</span></span>  
  
3.  <span data-ttu-id="fcade-130">En la página **script** del editor de la **tarea script**, agregue ambas variables a la `ReadOnlyVariables` propiedad.</span><span class="sxs-lookup"><span data-stu-id="fcade-130">On the **Script** page of the **Script Task Editor**, add both variables to the `ReadOnlyVariables` property.</span></span>  
  
4.  <span data-ttu-id="fcade-131">En el proyecto de script, establezca una referencia al espacio de nombres `System.Drawing`.</span><span class="sxs-lookup"><span data-stu-id="fcade-131">In the script project, set a reference to the `System.Drawing` namespace.</span></span>  
  
5.  <span data-ttu-id="fcade-132">En el código, utilice las instrucciones `Imports` para importar los espacios de nombres `System.Drawing` y `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="fcade-132">In your code, use `Imports` statements to import the `System.Drawing` and `System.IO` namespaces.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-multiple-image-files"></a><span data-ttu-id="fcade-133">Para configurar este ejemplo de la tarea Script para su uso con varios archivos de imagen</span><span class="sxs-lookup"><span data-stu-id="fcade-133">To configure this Script Task example for use with multiple image files</span></span>  
  
1.  <span data-ttu-id="fcade-134">Coloque la tarea Script dentro de un contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="fcade-134">Place the Script task within a Foreach Loop container.</span></span>  
  
2.  <span data-ttu-id="fcade-135">En la página **Colección** del **Editor de bucles Para cada uno**, seleccione como **Enumerador** el **Enumerador de archivos Para cada uno** y especifique la ruta de acceso y la máscara de archivo de los archivos de código fuente, como "\*.jpg".</span><span class="sxs-lookup"><span data-stu-id="fcade-135">On the **Collection** page of the **Foreach Loop Editor**, select the **Foreach File Enumerator** as the **Enumerator**, and specify the path and file mask of the source files, such as "\*.jpg."</span></span>  
  
3.  <span data-ttu-id="fcade-136">En la página **Asignaciones de variables**, asigne la variable `CurrentImageFile` al índice 0.</span><span class="sxs-lookup"><span data-stu-id="fcade-136">On the **Variable Mappings** page, map the `CurrentImageFile` variable to Index 0.</span></span> <span data-ttu-id="fcade-137">Esta variable pasa el nombre de archivo actual a la tarea Script de cada iteración del enumerador.</span><span class="sxs-lookup"><span data-stu-id="fcade-137">This variable passes the current file name to the Script task on each iteration of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcade-138">Estos pasos son adicionales a los enumerados en el procedimiento para el uso con un archivo de imagen único.</span><span class="sxs-lookup"><span data-stu-id="fcade-138">These steps are in addition to the steps listed in the procedure for use with a single image file.</span></span>  
  
### <a name="example-2-code"></a><span data-ttu-id="fcade-139">Código de ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="fcade-139">Example 2 Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim currentImageFile As String  
    Dim currentImage As Image  
    Dim maxThumbSize As Integer  
    Dim thumbnailImage As Image  
    Dim thumbnailFile As String  
    Dim thumbnailHeight As Integer  
    Dim thumbnailWidth As Integer  
  
    currentImageFile = Dts.Variables("CurrentImageFile").Value.ToString  
    thumbnailFile = Path.Combine( _  
        Path.GetDirectoryName(currentImageFile), _  
        String.Concat(Path.GetFileNameWithoutExtension(currentImageFile), _  
        "_thumbnail.jpg"))  
  
    Try  
        currentImage = Image.FromFile(currentImageFile)  
  
        maxThumbSize = CType(Dts.Variables("MaxThumbSize").Value, Integer)  
        CalculateThumbnailSize( _  
            maxThumbSize, currentImage, thumbnailWidth, thumbnailHeight)  
  
        thumbnailImage = currentImage.GetThumbnailImage( _  
           thumbnailWidth, thumbnailHeight, Nothing, Nothing)  
        thumbnailImage.Save(thumbnailFile)  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, "Script Task Example", _  
        ex.Message & ControlChars.CrLf & ex.StackTrace, _  
        String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
  
Private Sub CalculateThumbnailSize( _  
    ByVal maxSize As Integer, ByVal sourceImage As Image, _  
    ByRef thumbWidth As Integer, ByRef thumbHeight As Integer)  
  
    If sourceImage.Width > sourceImage.Height Then  
        thumbWidth = maxSize  
        thumbHeight = CInt((maxSize / sourceImage.Width) * sourceImage.Height)  
    Else  
        thumbHeight = maxSize  
        thumbWidth = CInt((maxSize / sourceImage.Height) * sourceImage.Width)  
    End If  
  
End Sub  
```  
  
```csharp  
bool ThumbnailCallback()  
        {  
            return false;  
        }  
        public void Main()  
        {  
  
            string currentImageFile;  
            Image currentImage;  
            int maxThumbSize;  
            Image thumbnailImage;  
            string thumbnailFile;  
            int thumbnailHeight = 0;  
            int thumbnailWidth = 0;  
  
            currentImageFile = Dts.Variables["CurrentImageFile"].Value.ToString();  
            thumbnailFile = Path.Combine(Path.GetDirectoryName(currentImageFile), String.Concat(Path.GetFileNameWithoutExtension(currentImageFile), "_thumbnail.jpg"));  
  
            try  
            {  
  
                currentImage = Image.FromFile(currentImageFile);  
  
                maxThumbSize = (int)Dts.Variables["MaxThumbSize"].Value;  
                CalculateThumbnailSize(maxThumbSize, currentImage, ref thumbnailWidth, ref thumbnailHeight);  
  
                Image.GetThumbnailImageAbort myCallback = new Image.GetThumbnailImageAbort(ThumbnailCallback);  
  
                thumbnailImage = currentImage.GetThumbnailImage(thumbnailWidth, thumbnailHeight, ThumbnailCallback, IntPtr.Zero);  
                thumbnailImage.Save(thumbnailFile);  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                Dts.Events.FireError(0, "Script Task Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
        }  
  
        private void CalculateThumbnailSize(int maxSize, Image sourceImage, ref int thumbWidth, ref int thumbHeight)  
        {  
  
            if (sourceImage.Width > sourceImage.Height)  
            {  
                thumbWidth = maxSize;  
                thumbHeight = (int)(sourceImage.Height * maxSize / sourceImage.Width);  
            }  
            else  
            {  
                thumbHeight = maxSize;  
                thumbWidth = (int)(sourceImage.Width * maxSize / sourceImage.Height);  
  
            }  
  
        }  
  
```  
  
<span data-ttu-id="fcade-140">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="fcade-140">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="fcade-141">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="fcade-141">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="fcade-142">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="fcade-142">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="fcade-143">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="fcade-143">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
