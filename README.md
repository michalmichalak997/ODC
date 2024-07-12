# OCT
A software OCT (Orientation Computing Tool) computes the local orientations of a geological contact using Delaunay triangulation. This code is related to the following paper accepted for publication in Computers&Geosciences:
"Using Delaunay triangulation and cluster analysis to determine the orientation of a sub-horizontal and noise including contact in Kraków-Silesian Homocline, Poland". The code was written in C++. For more information, see the UserManual.
The authors of the paper are: 
1. Michał Michalak (mimichalak@us.edu.pl), Department of Applied Geology, Faculty of Earth Sciences, University of Silesia in Katowice, Poland.
2. Waldemar Bardziński (waldemar.bardzinski@us.edu.pl), Department of Fundamental Geology, Faculty of Earth Sciences, University of Silesia in Katowice, Poland.
3. Lesław Teper (leslaw.teper@us.edu.pl), Department of Applied Geology, Faculty of Earth Sciences, University of Silesia in Katowice, Poland.
4. Zbigniew Małolepszy (zbigniew.malolepszy@pgi.gov.pl), Polish Geological Institute – National Research Institute Upper Silesian Branch.

Abstract. 
In this work, we combined a three-point problem with Delaunay triangulation to determine the average orientation of a sub-horizontal contact lying within the Kraków-Silesian Homocline, Poland. This contact was assumed to represent the regional trend due to the conformable or sub-conformable relationships between the geological units. The approach presented involved computing the local orientation of Delaunay triangles that represented the investigated surface. A C++ application was developed to compute the required figures, to which we added computer code that is open source and freely available. The pre-processing stage required the removal of collinear configurations that contributed to floating-point arithmetic inaccuracies. We then assigned dip angle and direction to the Delaunay triangles and performed a stereographic projection of the unit normal vectors. For statistical analysis, we conducted inertia moment analysis and followed the mean vector approach. As a part of exploring the orientation data—and as a way of achieving better consistency between stereonet results—we used several clustering algorithms: k-means, k-medoids and hierarchical. We indicated that the Euclidean distance could be beneficial for extracting the dominant orientation calculated for the sub-population assumed to represent the regional trend. We concluded that considering four clusters and the combination of the Euclidean distance and Ward linkage methods gave us the best extraction results for the dominant orientation. We identified limitations to the proposed approach relating to the lack of statistical information on the calculated orientations and suggested potential extensions to the research, including mixture models and investigation of spatial patterns.




%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%
%   ORIENTATION COMPUTING TOOL is distributed in the hope that it will be useful,
%   but WITHOUT ANY WARRANTY.  See the
%   GNU General Public License for more details.
%
% AUTHOR
%   Michalak Michał  mimichalak@us.edu.pl
%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%


# Instruction

## 1. Install Microsoft Visual Studio and CGAL library. The instructions with CGAL installation can be found here:

https://www.cgal.org/download/windows.html

Alternatively, you can contact Michal Michalak and ask for an executable. KYC and AML procedures will be applied.

## 2. Prepare your input data in the following format:

Example 1.
X | Y| Z | id
--- | --- | --- | ---
| 919016.62 | 254566.13 | 196.04 | 1 |
| 919027.75 | 252559.20 | 237.19 | 2 |
| 919042.29 | 253658.44 | 231.49 | 3 |
| 919081.62 | 253445.45 | 234.78 | 4 |
| 919094.57 | 253812.40 | 227.02 | 5 |

Example 2.
X | Y| Z1 | Z2 | id
--- | --- | --- | --- | ---
| 919016.62 | 254566.13 | 196.04 | 189.09 | 1 |
| 919027.75 | 252559.20 | 237.19 | 121.30 | 2 |
| 919042.29 | 253658.44 | 231.49 | 201.11 | 3 |
| 919081.62 | 253445.45 | 234.78 | 211.98 | 4 |
| 919094.57 | 253812.40 | 227.02 | 234.30 | 5 |



Note:

- X corresponds to latitude, Y corresponds to longitude, Z corresponds to elevation, id corresponds to the number of point
- the first example contains one surface and the second example contains two surfaces
- the above set contains five boreholes, each defined by XYZ coordinates
- the last column must be the index
- the Cartesian coordinates XYZ are separated by space
- the use of decimal point within a coordinate is allowed
- remove header (X Y Z id) prior to executing the program
- the file should be saved as .txt


## 3. Open Microsoft Visual Studio, paste the code (SourceCode) and run it.

- Specify the number of input surfaces
- 
- Type in the path of your input data and press ENTER. The following format should be applied:
C:\dev\CGAL-4.8\examples\Triangulation_2\JurassicBottomInput.txt

- Type in the path of the output and press ENTER. The following format should be applied:
C:\dev\CGAL-4.8\examples\Triangulation_2\JurassicBottomOutput.txt

![program-realdata](https://github.com/user-attachments/assets/ba16ce87-9e98-4991-a376-75c0373c0ae8)

## 4. Your output files are ready for further processing including .vtu files for ParaView.


