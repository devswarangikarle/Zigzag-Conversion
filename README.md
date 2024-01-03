# Zigzag-Conversion

class Solution:
    def convert(self, s, numRows):
        if numRows == 1 or numRows >= len(s):
            return s

        result = [''] * numRows
        index, step = 0, 1

        for char in s:
            result[index] += char

            if index == 0:
                step = 1
            elif index == numRows - 1:
                step = -1

            index += step

        return ''.join(result)


sol = Solution()

s1 = "PAYPALISHIRING"
numRows1 = 3
print(sol.convert(s1, numRows1))  

s2 = "PAYPALISHIRING"
numRows2 = 4
print(sol.convert(s2, numRows2)) 

s3 = "A"
numRows3 = 1
print(sol.convert(s3, numRows3))  
