import os
import math
import time

size = os.get_terminal_size()

y = size.lines
x = size.columns

centre = [int(x/2), int(y/2)]
radius_centre = 30
radius_donut = 3

lightmap = ['.', ',', '!', '-', '+', '*', '/', 'x', '#', '@']

print(x, y)

class map():
    def __init__(self):
        self.clear_map()

    def render_map(self):
        rendered_line = ''
        for column in self.map:
            for line in column:
                rendered_line += line

            print(rendered_line)
            rendered_line = ''

    def clear_map(self):
        self.map = []
        for column in range(y):
            self.map.append([])
            for line in range(x):
                self.map[column].append(lightmap[0])

    def draw_circle(self, centre, x_radius, y_radius):
        full_angle = 360
        for angle in range(full_angle):
            x = int(x_radius * math.cos(angle) + centre[0])
            y = int(y_radius * math.sin(angle) + centre[1])

            self.edit_coordinate(x, y, lightmap[9])

    def edit_coordinate(self, x, y, value):
        # value (3, 0)
        self.map[y][x] = value

donut = map()
donut.edit_coordinate(centre[0], centre[1], lightmap[9])

for angle in range(2048):
    x_radius = abs(int(radius_centre * math.cos(angle*0.1)))
    y_radius = abs(int(radius_centre * math.cos(angle*0.05)))
    print(f"{angle}: radius length {x_radius}")
    
    donut.draw_circle(centre, x_radius, y_radius)
    donut.render_map()
    donut.clear_map()
    time.sleep(0.01)
