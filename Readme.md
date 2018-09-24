# Libreria de Reconocimiento Facial
Esta libreria utiliza el el Cognitive Service API para encontrar caras en las fotos.
Para ello, se utiliza la clase ```CognitiveFace```, la cual recibe por parametro una imagen (path) y la envia a la API para ver detectar si la misma contiene o no una cara. En caso de encotrar una, la propiedad ```FaceFound``` indicará el resultado y la libreria almacenará una nueva copia de la imagen bajo el nombre tmpFace.jpg con un recuadro dibujado alrededor del rostro.

### Ejemplo de uso:
```c#
static void Main(string[] args)
{
    //Se debe pasar por parametro la API Key y el color del recuadro a dibujar 
    //en caso de encontrar una cara en la foto
    CognitiveFace cog = new CognitiveFace("<api-key>", Color.GreenYellow);
    cog.Recognize(@"bill.jpg");
    FoundFace(cog);
    cog.Recognize(@"yacht.jpg");
    FoundFace(cog);
}
static void FoundFace(CognitiveFace cog)
{
    if (cog.FaceFound)
        Console.WriteLine("Face Found! :)");
    else
        Console.WriteLine("No Face Found :(");
} 
```