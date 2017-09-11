# some_coders_online-s-code
my code. 

import random as r
import matplotlib.pyplot as mlp

def mid_point(point1, point2):

    point3x = (point1[0] + point2[0]) / 2
    point3y = (point1[1] + point2[1]) / 2

    point3 = [point3x, point3y]
    return point3

def point_gen(repeates):
    pointx = [-3,0,3,0]
    pointy = [0,3,0,0]

    on = True
    while on:
        new_pointx = pointx[-1]
        new_pointy = pointy[-1]
        number = r.randrange(1,7)
        point2 = [new_pointx, new_pointy]

        if number == 1 or number == 2:
            point1x = pointx[0]
            point1y = pointy[0]
        elif number == 3 or number == 4:
            point1x = pointx[1]
            point1y = pointy[1]
        else:
            point1x = pointx[2]
            point1y = pointy[2]

        point1 = [point1x, point1y]

        new_point = mid_point(point1,point2)

        pointx.append(new_point[0])
        pointy.append(new_point[1])

        if len(pointx) > repeates:
            on = False
            return pointx, pointy

points = point_gen(100000)

mlp.plot(points[0],points[1],'*')
mlp.show()

