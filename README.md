# Liu
利用动态数组解决数据存放问题
def A(N):
    array = []
    for i in range(1,N+1):
        if i % 5 == 0 or i % 7 == 0:
            array.append(i)
    return a




托普利茨矩阵问题
public class Solution {
    public bool IsToeplitzMatrix(int[,] matrix) {
         bool _isMatch=true;        
       for(int i=0;i<matrix.GetLength(0)-1;i++)
       {           
          for(int j=0;j<matrix.GetLength(1)-1;j++)
          {              
              if(matrix[i,j]!=matrix[i+1,j+1])
              {
                 _isMatch=false;
                  break;
              }
          }
           
           if(!_isMatch){
               break; 
           }                      
       }        
        return _isMatch;
    }
}

三数之和
class Solution:
    def threeSum(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        if len(nums)<3: return []
        nums = sorted(nums)
        if nums[0]==nums[-1] and nums[0]==0:return [[0,0,0]]
        if nums[0]==nums[-1] and nums[0]!=0:return [] 
        lis = []
        dic = {}
        for i in range(len(nums)):
            if nums[i] not in dic:
                dic[nums[i]] = i
        for target in range (len(nums)):
            for i in range (target+1,len(nums)):
                    q = -(nums[target] + nums[i])
                    w = nums[target]
                    e = nums[i]
                    if q in dic and dic[q] != i and dic[q] != target:
                        lis.append(sorted([w,e,q]))
        turn_list = []
        dic = {}
        for i in lis:
            if str(i) not in dic:
                dic[str(i)] = 1
                turn_list.append(i)
        return turn_list
