# TechnicalDocs
Technial Coading Documentations
# ｕｓｉｎｇ ｂｅｔｓ ａｎｄ ｅｐｓ ｉｎ ｔｈｉｓ ｃｏｄｅ
# 𝗈𝗉𝗍𝗂𝗆𝗂𝗓𝖾𝗋 = 𝗈𝗉𝗍𝗂𝗆.𝖠𝖽𝖺𝗆(𝗆𝗈𝖽𝖾𝗅.𝗉𝖺𝗋𝖺𝗆𝖾𝗍𝖾𝗋𝗌(), 𝗅𝗋=𝖼𝗈𝗇𝖿𝗂𝗀["𝗍𝗋𝖺𝗂𝗇𝗂𝗇𝗀"]["𝗅𝖾𝖺𝗋𝗇𝗂𝗇𝗀_𝗋𝖺𝗍𝖾"], 𝖻𝖾𝗍𝖺𝗌=(0.9, 0.98), 𝖾𝗉𝗌=1𝖾-9)
betas: This is a tuple of two elements (beta1, beta2). These are the exponential decay rates for the first moment estimates and the second moment estimates, respectively. They are used to compute running averages of gradient and its square for Adam optimizer. The values are usually close to 1. Typical values are (0.9, 0.999).

eps: This is a very small number to prevent any division by zero in the implementation (known as epsilon). It's used to maintain numerical stability, as it avoids division by zero or too small numbers when the denominator in the Adam algorithm becomes very small.

In the Adam optimization algorithm, these parameters control how fast the algorithm converges and can have a significant impact on the performance of the model. They are usually set to their default values and not tuned, but they can be adjusted if necessary.


# Ｕｓｉｎｇ Ｏｆ Ｗｉｎｄｏｗ Ｉｎ Ｔｈｉｓ Ｆｕｎｃｔｉｏｎ
# def prepare_data_x(x, window_size):
#    # perform windowing
#    n_row = x.shape[0] - window_size + 1
#    output = np.lib.stride_tricks.as_strided(x, shape=(n_row, window_size), strides=(x.strides[0], x.strides[0]))
#    return output[:-1], output[-1]

In the context of this code, window_size is a parameter that determines the number of consecutive data points to consider as one "window" or "frame" of data.

This technique is often used in time series analysis and machine learning, where it's important to consider not just individual data points, but also their context within a sequence of data. For example, if you're predicting stock prices, it might be useful to consider not just today's price, but also the prices over the past window_size days.

In this specific function, prepare_data_x(x, window_size), the input data x is being reshaped into a 2D array where each row is a window of window_size consecutive elements from x. The function returns two arrays: one with all but the last window, and one with just the last window.

For example, if x = [1, 2, 3, 4, 5, 6] and window_size = 3, the function would return ([1, 2, 3], [2, 3, 4], [3, 4, 5]) and [4, 5, 6].


# Ｕｓｉｎｇ Ｏｆ Ｓｔｅｐ Ｓｉｚｅ ａｎｄ ｇａｍｍａ
# scheduler = optim.lr_scheduler.StepLR(optimizer, step_size=config["training"]["scheduler_step_size"], gamma=0.1)
This line of code is creating a learning rate scheduler for the optimizer in a PyTorch model. Let's break it down:

scheduler = optim.lr_scheduler.StepLR(...): This is creating an instance of the StepLR class from the torch.optim.lr_scheduler module, and assigning it to the variable scheduler.

optimizer: This is the optimizer object for which you want to adjust the learning rate. It could be any PyTorch optimizer like Adam, SGD, etc.

step_size=config["training"]["scheduler_step_size"]: This is setting the number of epochs after which the learning rate should be decreased. The value is being fetched from a configuration dictionary.

gamma=0.1: This is the factor by which the learning rate should be multiplied after step_size epochs. In this case, the learning rate is being multiplied by 0.1, effectively reducing it to 10% of its current value.

1770
3540


Airfiver
5240 6 Month
1000 installation


<!-- https://tools.picsart.com/text/font-generator/ -->


https://medium.com/@prajjwalchauhan94017/stock-prediction-and-forecasting-using-lstm-long-short-term-memory-9ff56625de73
https://github.com/mwitiderrick/stockprice/?source=post_page-----9ff56625de73--------------------------------

https://www.youtube.com/results?search_query=stock+prediction+with+ai
https://www.youtube.com/watch?v=fGLY0dIHJ2w
https://github.com/rohan472000/reliance-stock-price-prediction-LSTM/blob/main/price_prediction.ipynb

# Migrate Flask Database
    set FLASK_APP=models.py
    flask db init
    flask db migrate -m "Initial migration"
    flask db upgrade


https://www.youtube.com/watch?v=WxYC9-hBM_g    
