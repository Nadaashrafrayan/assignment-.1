# assignment-.1
// Course:  CS213 - Programming II  - 2018
// Title:   Assignment I - Task 1 - Problem 1
// Program: CS213-2018-A1-T1-P1
// Purpose: Skeleton code for the student to start working
// Author:  Dr. Mohammad El-Ramly
// Date:    10 August 2018
// Version: 1.0

#include <iostream>
#include <iomanip>
//#include <cassert>

using namespace std;

// A structure to store a matrix
struct matrix
{
  int* data;       // Pointer to 1-D array that will simulate matrix
  int row, col;
};

// Already implemented
void createMatrix (int row, int col, int num[], matrix& mat);

// Student #1 with the smallest ID (e.g., 20170080)
// All these operations return a new matrix with the calculation result
matrix operator+(matrix mat1,matrix mat2){
    matrix mat17;
    createMatrix(mat1.row,mat1.col,mat17.data,mat17);
    for(int i=0;i<mat1.row;i++){
		for(int j=0;j<mat1.col;j++)
			 mat17.data[i]=mat1.data[i]+mat2.data[i])}
	}	
	return mat17;
}
matrix operator-(matrix mat1,matrix mat2){
    matrix mat17;
    createMatrix(mat1.row,mat1.col,mat17.data,mat17);
    for(int i=0;i<mat1.row;i++){
		for(int j=0;j<mat1.col;j++)
			 mat17.data[i]=mat1.data[i]-mat2.data[i])}
	}
	return mat17;
}
matrix operator+(matrix mat1,int scalar){
    matrix mat17;
    createMatrix(mat1.row,mat1.col,mat17.data,mat17);
    for(int i=0;i<mat1.row;i++){
		for(int j=0;j<mat1.col;j++)
			 mat17.data[i]=mat1.data[i]+scalar)}
	}
	return mat17;
}
matrix operator-(matrix mat1,int scalar){
    matrix mat17;
    createMatrix(mat1.row,mat1.col,mat17.data,mat17);
    for(int i=0;i<mat1.row;i++){
		for(int j=0;j<mat1.col;j++)
			 mat17.data[i]=mat1.data[i]-scalar)}
	}
	return mat17;
}


// Student #2 with the middle ID (e.g., 20170082)
// The last operator >> takes an istream and a matrix and return the
// the same istream so it is possible to cascade input like
// cin >> matrix1 >> matrix2 << endl;
matrix operator-=(int scalar){//this operator change the matrix and return the new.
    for(int i=0;i<matSize;i++)
         mat1.data[i]-=scalar;
	cout<<mat1.data[i]<<endl;
}
matrix operator-=(matrix mat1,matrix mat2){ // this operator subtract right operand from the left then assign the result to the left operandand this op is the combination of - and = it sub the value of the variable on left from the value on right and then assign the rsult to the variable on left.
    for(int i=0;i<matSize;i++)
         mat1.data[i]-=mat2.data[i];
	cout<<mat1.data[i]<<endl;
}
matrix operator--(int matrix){ // Sub 1 from each element --mat 
   for(int i=0;i<matSize;i++)
           mat1.data[i]++;
	cout<<mat1.data[i]<<endl;
}
matrix operator+=(int scalar){//this operator change the matrix and return the new.
    for(int i=0;i<matSize;i++)
         mat1.data[i]+=scalar;
	cout<<mat1.data[i]<<endl;
}
matrix operator+=(matrix mat1,matrix mat2){//return the result by using refrence but the operator+ copy the result...this operator add right operand to the left then assign the result to left operandand this op is the combination of + and = it add the value of the variable on left to the value on right and then assign the rsult to the variable on left.
    for(int i=0;i<matSize;i++)
         mat1.data[i]+=mat2.data[i];
	cout<<mat1.data[i]<<endl;
}	
matrix operator++(int matrix){ // Add 1 to each element ++mat  
   for(int i=0;i<matSize;i++)
           mat1.data[i]++;
	cout<<mat1.data[i]<<endl;
}


//Student #3 with the biggest ID (e.g., 20170089)
ostream& operator<< (ostream& out, matrix mat){
	for(int i=0 ; i<mat.row*mat.col ; i++){
		out<< mat.data[i]<< " ";
		if(i%(mat.col-1) == 0){
			out<< endl;
		}
	}
};
bool   operator== (matrix mat1, matrix mat2){
	if(mat1.col==mat2.col && mat1.row==mat2.row){
		for(int i=0 ; i<mat1.row*mat1.col ; i++){
			if(mat1.data[i] != mat2.data[i]){
				return false;
			}
		}
	}
	else{
		return false;
	}
	return true;
};
bool   operator!= (matrix mat1, matrix mat2){
	return !(mat1 == mat2);
};
bool   isSquare   (matrix mat);{
	return mat.col == mat.row;
};
bool   isSymetric (matrix mat){
	if(mat.isSquare()){
		for(int i=0 ; i<mat.row*mat.col ; i++){
			if(mat.row*i > mat.row*mat.col-1){
				if(mat.data[i] != mat.data[(i*row)%(mat.row*mat.col-1)]){
					return false;
				}
			}
			else{
				if(mat.data[i] != mat.data[i*row]){
					return false;
				}
			}
		}
	}
	else{
		return false;
	}
	return true;
};
bool   isIdentity (matrix mat){
	if(mat.isSquare()){
		for(int i=0 ; i<mat.col*mat.row ; i++){
			if(i%(mat.row+1)==0 && mat.data[i]==1){
				continue;
			}
			else if(i%(mat.row+1)!=0 && mat.data[i]==0){
				continue;
			}
			else{
				return false;
			}
		}
	}
	else{
		return false;
	}
	return true;
};
matrix transpose(matrix mat){
	matrix mat1;
	mat1.row = mat.col;
	mat1.col = mat.row;
	int k = 1, j = 0;
	for(int i=0 ; i<mat.row*mat.col ; i++){
		mat1.data[i] = mat[j];
		j += mat.col;
		if(j >= mat.row*mat.col){
			j = k;
			k++;
		}
	}
};

//__________________________________________

int main()
{
  int data1 [] = {1,2,3,4,5,6,7,8};
  int data2 [] = {13,233,3,4,5,6};
  int data3 [] = {10,100,10,100,10,100,10,100};

  matrix mat1, mat2, mat3;
  createMatrix (4, 2, data1, mat1);
  createMatrix (2, 3, data2, mat2);
  createMatrix (4, 2, data3, mat3);

/* The next code will not work until you write the functions
  cout << mat1 << endl;
  cout << mat2 << endl;
  cout << mat3 << endl;

  cout << (mat1 + mat3) << endl << endl;
  cout << (mat3 + mat3) << endl << endl;

  ++mat1;
  cout << mat1 << endl;

  mat1+= mat3 += mat3;
  cout << mat1 << endl;
  cout << mat2 << endl;
  cout << mat3 << endl;
  // Add more examples of using matrix
  // .......
*/
  return 0;
}

//__________________________________________
// Takes an array of data and stores in matrix according
// to rows and columns
void createMatrix (int row, int col, int num[], matrix& mat) {
  mat.row = row;
  mat.col = col;
  mat.data = new int [row * col];
  for (int i = 0; i < row * col; i++)
    mat.data [i] = num [i];
}
