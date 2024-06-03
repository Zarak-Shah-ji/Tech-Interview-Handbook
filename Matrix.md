# In place Transpose:

    for i in range(row):
            # start from i else the whole matrxi re- swaped to original matrix
            for j in range(i,col):
                #swap
                matrix[i][j], matrix[j][i] = matrix[j][i], matrix[i][j]
      
