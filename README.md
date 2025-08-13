class Solution :
    def generateParenthesis(self,curr_str,Open,Close,ans,n):
        if(Open+Close==2*n and Open==Close):
            ans.append(curr_str)
            return
        if(Open>n):
            return
        if(Close>Open):
            return
        self.generate(curr_str+"(",Open+1,Close,ans,n)
        self.generate(curr_str+")",Open,Close+1,ans,n)
    def generateParenthesis(self,n:int) -> list[str]:
        curr_str =""
        ans=[]
        Open =0
        Close =0
        self.generate(curr_str,Open,Close,ans,n)
        return ans
ob=Solution()
n=int(input())
print(ob.generateParenthesis(n))
