# task
def are_braces_balanced(input_string):
    
    stack = []
    
    brace_map = {')': '(', '}': '{', ']': '['}
    
    for char in input_string:
        if char in "({[":
            
            stack.append(char)
        elif char in ")}]":
            
            if not stack or stack[-1] != brace_map[char]:
                return False
            stack.pop()  

    # If the stack is empty, all braces are balanced
    return len(stack) == 0


