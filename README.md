# pyautocad_examples
this repository contains python code using pyautocad

import pyautocad
import math

from pyautocad import Autocad, APoint

# Connect to AutoCAD application
acad = Autocad(create_if_not_exists=True)

rs = 100

acad.prompt("Drawing {0} circles".format(rs))

steps_count = 8
gap = (int)(rs / steps_count)

for j in range(0, rs, gap):
    x = math.sqrt((rs ** 2) - (j ** 2))
    acad.model.AddCircle(APoint(0, 0, j), x)
    acad.model.AddCircle(APoint(0, 0, -j), x)

    ![image](https://github.com/user-attachments/assets/1b604490-58e5-4fa5-99c9-9bd3dbcfb47b)
