# B.Tech-Final-year-Project
*Project on application of Estimation algorithms in Chemical Engineering*

<body>
    <h1>Chemical Engineering and Estimation Algorithms</h1>
    <p>Chemical engineering is a discipline that applies mathematical models and techniques to optimize chemical processes. It requires a deep understanding of chemistry, physics, and mathematics.</p>
    <p>One valuable technique in chemical engineering is application filtering. This mathematical method estimates system states and predicts future values based on past measurements.</p>
    <h3>Importance of Estimation Algorithms in Chemical Engineering</h3>
    <p>Chemical engineering deals with complex systems that require monitoring and control for optimal function. These systems often have multiple inputs and outputs, along with disturbances and uncertainties. To make informed control decisions, accurate estimates of system states are crucial.</p>
    <p>Kalman filters (KF), Extended Kalman Filters (EKF), and Unscented Kalman Filters (UKF) are powerful application filtering tools used in chemical engineering.</p>
    <h3>Types of Kalman Filters</h3>
    <ul>
        <li><strong>Kalman Filter (KF):</strong> This widely used technique estimates a system's state based on noisy measurements. It's a recursive algorithm that updates the state estimate with new measurements.
        <br>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Basic_concept_of_Kalman_filtering.svg/400px-Basic_concept_of_Kalman_filtering.svg.png" alt="Basic Concept of Kalman Filtering">
        </li>
        <li><strong>Extended Kalman Filter (EKF):</strong> An extension of the KF for non-linear systems. It approximates the non-linear system linearly and estimates the state using the same KF algorithm.</li>
        <li><strong>Unscented Kalman Filter (UKF):</strong> Another extension for non-linear systems. It uses unscented transformation to approximate the probability distribution of the state estimate. The UKF can be more accurate than the EKF, especially for highly non-linear systems.
        <br>
        <img src="Picture1.jpg"  width="300"> </li>
    </ul>
</body>

