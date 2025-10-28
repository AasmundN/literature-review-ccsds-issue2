# Disposition for litterature review

1. Introduce hyper spectral imaging and its relevance and importance. Here you should refere to the Hypso1 first images paper and the Ocean color remote sensing paper. This part should motivate why we care about these images.
2. Motivate why we need to compress the images. Put it in the context of hypso. Also write about the constraints faced by FPGA implementation. Need to use low area, low power, and high throughput in order to offload the CPU.
3. Transition to the CCSDS compression standards. Mention issue 1.
4. Give a generic overview of the algorithm: predictor and encoder.
5. Introduce issue 2. Compare with issue 1. Refer to the algorithm specification.
6. Refer to paper on Johans implementation of issue 1. High throughput and widely used in active space applications (find a source on that?).
7. Digg a bit deeper into how issue 2 works. Give a nice data flow graph of the predictor. This is to motivate why this version is harder to implement with high throughput.
8. Mention early attempts at implementing on FPGA and the low throughput (find reference).
9. Loose ordering here. Refer to respective paper for all of them.
    - Mention the big boi implementation, high throughput at the cost of a lot of hardware. Splits the image.
    - Barrios suggests skipping weight updates, and selecting these separately.
    - Sánchez suggests speculatively calculating the weight update, thus allowing better pipelining.
        - This approach implemented by Vorhaug and has been tested on a Hypso satellite.
    - Newest development: periodic weight updating. Explain this and how it potentially can increase the throughput. Has not been tested in a space application yet.
