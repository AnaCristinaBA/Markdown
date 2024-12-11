Cas Pràctic 1. L'ordre diff

Pas 1. Creació dels fitxers de base

    Projecte1
    #Projecte nou per a un cas pràctic
    Aquesta és la primera versió del document del nou projecte.    

    Projecte2
    #Projecte nou per a un cas pràctic
    Aquesta és la segona versió del document del nou projecte.
    Esta es una nova línea del projecte.

Pas 2. Ús de diff

$ diff projecte1 projecte2
    0a1
    > 
    3c4,5
    < Aquesta és la primera versió del document del nou projecte.
    ---
    > Aquesta és la segona versió del document del nou projecte.
    > Esta es una nova línea del projecte.   

Comparació de dos imatges
    $ diff pza_grabado.jpg istockphoto-1620326531-612x612.jpg 
    Los archivos binarios pza_grabado.jpg y istockphoto-1620326531-612x612.jpg son distintos

