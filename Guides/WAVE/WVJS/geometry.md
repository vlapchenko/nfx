# WAVE.Geometry

## Properties

* EARTH_RADIUS_KM : 6371
* PI : 3.14159265
* PI2 : 6.28318531
* MapDirection:   
{
  North:     {Name: "North"},
  NorthEast: {Name: "NorthEast"},
  East:      {Name: "East"},
  SouthEast: {Name: "SouthEast"},
  South:     {Name: "South"},
  SouthWest: {Name: "SouthWest"},
  West:      {Name: "West"},
  NorthWest: {Name: "NorthWest"}
}


## Functions

##### angleToMapDirection(float angle): MapDirection
Converts a radian angular coordinate into map direction

##### azimuthDeg(float xc, float yc, float xd, float yd): float
Returns azimuth angle (theta) in degrees.

##### azimuthDegPoints(Point pc, Point pd)
Returns azimuth angle (theta) in degrees for two points: center and destination.

##### azimuthOfRadix(float xc, float yc, float xd, float yd, int radix): int
Returns azimuth angle (theta) in radix units.

##### azimuthOfRadixPoints(Point pc, Point pd, int radix): int
Returns azimuth angle (theta) in in radix units for two points: center and destination . 

##### azimuthRad(float xc, float yc, float xd, float yd): float
Returns azimuth angle (theta) in radians.

##### azimuthRadPoints(Point pc, Point pd)
Returns azimuth angle (theta) in radians for two points: center and destination.

##### degToRad(int deg): float
Converts degrees to rads.

##### distance(float x1, float y1, float x2, float y2): float
Returns pixel distance between two points.

##### distancePoints(Point p1, Point p2): float
Returns pixel distance between two points.

##### findRayFromRectangleCenterSideIntersection(Rectangle rect, float theta): Point
Returns a point of intersection between a ray cast from the center of a rectangle under certain polar coordinate angle and a rectangle side.

##### getBBox(points): Rectangle
Returns 2D bounding box (with for a set of points (array of {x, y}).

##### lineIntersectsRect(float rx1, float ry1, float rx2, float ry2, float lx1, float ly1, float lx2, float ly2): bool
Defines if line has common points with rectangle (top-left/bottom-right coordinates).

##### mapDirectionToAngle(MapDirection direction): float
Converts map direction to angular coordinate in radians.

##### overlapAreaRect(Rectangle rect1, Rectangle rect2): float
Returns area of overlap between two rectangles.

##### overlapAreaWH(float x1, float y1, float w1, float h1, float x2, float y2, float w2, float h2): float
Returns area of overlap between two rectangles expressed as top-left/width-height pairs.

##### overlapAreaXY(float left1, float top1, float right1, float bott1, float left2, float top2, float right2, float bott2): float
Returns area of overlap between two rectangles expressed as top-left/bottom-right pairs.

##### perimeterViolationArea(Rectangle perimeter, Rectangle inner): float
Calculates a relative area of an inner rectangle that violates outside perimeter. The area is not 100% geometrically accurate - may be used for relative comparisons only.

##### radToDeg(float rad): float
Converts radians to degrees.

##### rotateRectAroundCircle(float cx, float cy, float cMargin, float rw, float rh, float angle): Rectangle
Calculates coordinates of rectangle given by width/height (`rw/`rh`) which center is rotated by `angle` (in radians) relatively to point (`cx`/`cy`) respecting rectangle size and `cMargin`. Returns coordinates of rotated rectangle.

##### toRectWH(float x1, float y1, float w, float h): Rectangle
Returns rectangle from coordinates and dimensions (width and height).

##### toRectXY(float x1, float y1, float x2, float y2): Rectangle
Returns rectangle from coordinate pairs.

##### wrapAngle(float angle, float delta): float
Modifies an angle by delta value ensuring that resulting angle is always between 0 and 2pi.


## Classes

### Point
Represents x,y pair on a Cartesian plane.
##### Point(float x, float y)
Constructor.
##### isEqual(Point p): bool
Determines whether the two points contain equivalent coordinates.
##### offset(float dx, float dy)
Changes point coordinates.
##### toPolarPoint(Point center): PolarPoint
Returns point as polar point relative to the specified center.
##### toString(): string
Returns coordinates in string like: `(10 , 12)`.
##### x(): float
Returns X coordinate.
##### y(): float
Returns Y coordinate.

### PolarPoint
Represents point with polar coordinates.
##### PolarPoint(float radius, float theta)
Constructor.
##### isEqual(PolarPoint p): bool
Determines whether the two points contain equivalent coordinates.
##### radius()
Returns radius of point.
##### theta()
Returns angle theta of point.


### Rectangle