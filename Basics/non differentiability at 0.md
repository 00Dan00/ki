- it means the function has a sharp corner or a cusp at that point
- it mean the derivative doesn't exist at that point and many algorithms, especially those based on gradiant descent, rely on the existence of derivatives to determine the direction and magnitude of adjustments to the parameters in order to minimize the error function.
- => can lead to the algorithm being stuck or unpredictable
- requires specialized optimization techniques 

this means we want smooth gradiants.
- always differentiable
- more stable and efficient training because the weight updates are proportional to the error, leading to more gradual and controlled learning