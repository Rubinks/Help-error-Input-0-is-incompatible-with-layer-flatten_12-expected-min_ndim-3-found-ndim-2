# Help-error-Input-0-is-incompatible-with-layer-flatten_12-expected-min_ndim-3-found-ndim-2
error in project in libraries Keras

MY CODE:
model.add(Flatten())
model.add(Dense(512, activation='relu'))
model.add(Dropout(0.5))
model.add(Dense(10, activation='softmax()'))

ERROR:
ValueError                                Traceback (most recent call last)
<ipython-input-43-e26b5e19959a> in <module>()
----> 1 model.add(Flatten())
      2 model.add(Dense(512, activation='relu'))
      3 model.add(Dropout(0.5))
      4 model.add(Dense(10, activation='softmax()'))

~/anaconda3_501/lib/python3.6/site-packages/keras/engine/sequential.py in add(self, layer)
    183                 self.inputs = network.get_source_inputs(self.outputs[0])
    184         elif self.outputs:
--> 185             output_tensor = layer(self.outputs[0])
    186             if isinstance(output_tensor, list):
    187                 raise TypeError('All layers in a Sequential model '

~/anaconda3_501/lib/python3.6/site-packages/keras/engine/base_layer.py in __call__(self, inputs, **kwargs)
    412                 # Raise exceptions in case the input is not compatible
    413                 # with the input_spec specified in the layer constructor.
--> 414                 self.assert_input_compatibility(inputs)
    415 
    416                 # Collect input shapes to build layer.

~/anaconda3_501/lib/python3.6/site-packages/keras/engine/base_layer.py in assert_input_compatibility(self, inputs)
    325                                      self.name + ': expected min_ndim=' +
    326                                      str(spec.min_ndim) + ', found ndim=' +
--> 327                                      str(K.ndim(x)))
    328             # Check dtype.
    329             if spec.dtype is not None:

ValueError: Input 0 is incompatible with layer flatten_12: expected min_ndim=3, found ndim=2
