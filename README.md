# LongestValidParentheses
answer the question called LongestValidParentheses from the website "LeetCode"

   <p><font size="7">Given a string containing just the characters '(' and ')',find the length of 
    the longest valid (well-formed) parentheses substring.For "(()", the longest 
    valid parentheses substring is "()", which has length = 2.Another example is 
    ")()())", where the longest valid parentheses substring is "()()", which has 
    length = 4.</font></p>
    <a href="https://leetcode.com/problems/longest-valid-parentheses/"></a>
    <p>Solution:<dr></p>
    <code>
    class Solution {
      public int longestValidParentheses(string s) {
        Stack<Integer> stack=new Stack<Integer>();
		
		int left=-1;
		for(int j=0;j<s.length();j++){
			if(s.charAt(j)=='(')
				stack.push(j);
			else{
				if(s.charAt(j)!=')'){
					break;
				}
				if(stack.isEmpty())
					left=j;
				else {
					stack.pop();
					if(stack.isEmpty())
						max=Math.max(max,j-left);
					else
						max=Math.max(max,j-stack.peek());
				}
			}
		}
    }
};
    </code>
