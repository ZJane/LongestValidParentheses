### LongestValidParentheses
answer the question called LongestValidParentheses from the website "LeetCode"

   <p><font size="7">Given a string containing just the characters '(' and ')',find the length of 
    the longest valid (well-formed) parentheses substring.For "(()", the longest 
    valid parentheses substring is "()", which has length = 2.Another example is 
    ")()())", where the longest valid parentheses substring is "()()", which has 
    length = 4.</font></p>
 
   <a href="https://leetcode.com/problems/longest-valid-parentheses/">链接</a>
    
    <h3>解题思路</h3>
    <p>在解这道题,我先推荐看一篇超赞的文章:“知其所以然之永不遗忘算法”,
    原文链接是
    <a href="http://selfboot.cn/2015/11/03/howto_find_algorithm/">链接</a>
    我是通过这篇文章,十分粗糙地理解了用有序栈来解这道题目的思路,鉴于自己地java编程能力仍旧捉急,
    另外我还参考了leetcode的讨论区,最后在讨论区的大神的代码在进行改动.(这种方法是可耻的,但
    由于时间精力原因，只能暂时这样,有机会再将自己敲出的代码copy上来).
    思路:1:维护一个栈,栈中存放整型对象;
         2:获取控制台输入的字符串的第j个字符,对其行判断,如果字符为“(”,将该字符的下标push
	 进栈中; 
	</p>
   
    <h3>Java code</h3>
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
    
