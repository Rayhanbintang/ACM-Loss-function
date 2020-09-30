def Active_Contour_Loss(logits, labels):

    pred = tf.nn.softmax(logits)

    loss = 0
    lambdaP = 10 # lambda parameter could be various.
    for i in range(0, 4):
        x = pred[:,1:,:,i] - pred[:,:-1,:,i] # horizontal and vertical directions
        y = pred[:,:,1:,i] - pred[:,:,:-1,i]

        delta_x = x[:,1:,:-2]**2
        delta_y = y[:,:-2,1:]**2
        delta_u = tf.abs(delta_x + delta_y)

        epsilon = 0.00000001 # where is a parameter to avoid square root is zero in practice.
        w = 1.

        lenth = w * tf.reduce_mean(tf.sqrt(delta_u + epsilon)) # equ.(11) in the paper

        C_1 = tf.ones((4, 224, 224))
        C_2 = tf.zeros((4, 224, 224))

        region_in = tf.abs(tf.reduce_mean(pred[:,:,:,i] * ((labels[:,:,:,i] - C_1)**2)) ) # equ.(12) in the paper
        region_out = tf.abs(tf.reduce_mean((1 - pred[:,:,:,i]) * ((labels[:,:,:,i] - C_2)**2))) # equ.(12) in the paper

        loss += lenth + lambdaP * (region_in + region_out)

    return loss
