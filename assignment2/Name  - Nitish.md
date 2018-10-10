![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/APJ.KALAM.jpeg)



**Name - Nitish.S**

**Batch - 3**





###                          NEURAL NETWORK METHODOLOGY



### OVERVIEW DIAGRAM OF NN



![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/Screenshot%20from%202018-10-10%2002-40-37.png)







### STEPS FOR NEURAL NETWORK METHODOLOGY

#### STEP 1 - Read Input and Output



![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step1.png)

X - Input pixel(4x3)

Y - Actual Output









#### **STEP**2  - Initalizing Weights and Biases

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step2.png)



wh - weight matrix to the hidden layer

bh - bias matrix to the hidden layer

  



#### **STEP**3  - Calculate Hidden Layers

Hidden_layer_Input = matrix(X * wh) + bh





![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step3.png)





#### **STEP**4  - Perform Non-linear Transformation on hidden layer input

Hidden_layer_activation = sigmoid(Hidden_layer_input)

Sigmoid = 1/(1 + exp(-x))

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step4.png)





#### **STEP**5  -Perform linear & Non-linear Transformation of hidden layer activation at outputlayer



Output_layer_input= Hidden_layer_activation * wout + bout

Output = Sigmoid(Output_layer_input)

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step5.png)









#### **STEP**6  - Calculate Gradient of Error(E) at output layer



Error = Y - Output



![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step6.png)







#### **STEP**7  - Compute slope at hidden and output layer



![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step7.png)

Slope_output_layer = derivatives_sigmoid(output) = sigmoid(output)*1-sigmoid(output)

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step7a.png)

Slope_hidden_layer = Derivatives_sigmoid(Hidden_layer_activation)

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step7b.png)





#### **STEP**8  - Compute delta at output layer

delta_output = E * Slope_output_layer * lr



![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step6.png)

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step7a.png)

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step8.png)





#### **STEP**9  -  Calculate Error at hidden layer

Error_at_hidden_layer = matrix_dot_product(d_output, wout.Transpose)

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step7.png)



![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step9.png)





#### **STEP**10  -  Compute delta at hidden  layer

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step7.png)



Slope_hidden_layer

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step7b.png)



Delta_hiddenlayer = Error_at_hidden_layer \* slope_hidden_layer

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step10.png)





#### **STEP**11  -  Update weight at both output and hidden layer



wout = wout + matrix_dot_product(hiddenlayer_activations.Transpose, d_output)*learning_rate

learning_rate = 0.1

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step11.png)





Hidden_layer_activation transpose

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step11c.png)

Delta_output

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step8.png)

wh =  wh+ matrix_dot_product(X.Transpose,d_hiddenlayer)*learning_rate

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step12.png)

Delta_hidden_layer 

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step10.png)







#### **STEP**12  -  Update biases at both output and hidden layer





bh = bh + sum(d_hiddenlayer, axis=0) \* learning_rate

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/STEP12.png)



*bout = bout + sum(d_output, axis=0)\*learning_rate*

![](https://raw.githubusercontent.com/Nitishsjce/EIP-2/7d9146659312373e02af05e4b62e14ef5d3032e0/assignment2/image/step12a.png)











​             