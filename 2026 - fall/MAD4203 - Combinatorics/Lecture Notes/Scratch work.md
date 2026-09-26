## Application 7 - PP strong form
A basket of fruit is being arranged out of apples, bananas, and oranges. What is the smallest number of pieces of fruit that should be put in the basket to guarantee that either there are at least eight apples or at least six bananas or at least nine oranges?

Either 8 apples, or 6 bannas, or 9 oranges?

Put in 8 apples, 6 bananas, 9 oranges, and one more fruit of any type?
by strong PP, 8 + 6 + 9 - 3(!) + 1 = 21 fruit
no matter how taken, always makes a group

taking out 3 removes redudancies (two or more fruits are both more than enough)

## Application 8
Two disks, one smaller than the other, are each divided into 200 congruent sectors. In the larger disk, 100 of the sectors are chosen arbitrarily and painted red; the other 100 sectors are painted blue. In the smaller disk, each sector is painted either red or blue with no stipulation on the number of red and blue sectors. The small disk is then placed on the larger disk so that their centers coincide. Show that it is possible to align the two disks so that the number of sectors of the small disk whose color matches the corresponding sector of the large disk is at least 100

100 red, 100 blue

if we fix the larger disk, 200 positions to rotate smaller disk

if we maximize the difference in all rotations then:
200 positions -> 101 difference on all

for every sector of fixed disk we see 100 of that color in the one we know of (no matter how many of each  color)
this is 20000 possibilities
so the average matchings per position is 20,000 / 200 = 100, so at least one must have at lesat 100 color matchings.