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
    <li>
      <strong>Kalman Filter (KF):</strong> This widely used technique estimates a system's state based on noisy measurements. It's a recursive algorithm that updates the state estimate with new measurements.
      <br>
      <img
        src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Basic_concept_of_Kalman_filtering.svg/400px-Basic_concept_of_Kalman_filtering.svg.png"
        alt="Basic Concept of Kalman Filtering" width="600px"
      />
      <sup>[1]</sup>
    </li>
    <li>
      <strong>Extended Kalman Filter (EKF):</strong> An extension of the KF for non-linear systems. It approximates the non-linear system linearly and estimates the state using the same KF algorithm.
    </li>
    <li>
      <strong>Unscented Kalman Filter (UKF):</strong> Another extension for non-linear systems. It uses unscented transformation to approximate the probability distribution of the state estimate. The UKF can be more accurate than the EKF, especially for highly non-linear systems.
      <br>
      <img src="Pictures/Picture1.jpg" alt="Custom Image" width="300" />
      <sup>[5]</sup>
    </li>
  </ul>
  <h3>Literature Referred</h3>
      <p>Kalman Filter has been an area of research for several decades and various papers have been published on it. While working on this project I referred to:</p>

<ol>
  <li>Constrained Nonlinear State Estimation Using Ensemble Kalman Filters <sup>[2]</sup></li>
  <li>Constrained nonlinear state estimation based on the UKF approach <sup>[3]</sup></li>
</ol>

<h4>Key Takeaways from Constrained Nonlinear State Estimation Using Ensemble Kalman Filters [2]:</h4>

<ul>
  <li>Proposed a constrained recursive formulation of the ensemble Kalman filter (EnKF) that retains the advantages of unconstrained EnKF while systematically dealing with bounds on the estimated state variables.</li>
  <li>The performance of the proposed constrained EnKF is compared with the performances obtained using the recursive constrained formulations available in the literature using two benchmark examples from the literature (a gas-phase reactor and an isothermal batch reactor), which involve constraints on the estimated state variables.</li>
  <li>When compared, the performance of the proposed C-EnKF formulation was found to be significantly better than those obtained using RNDDR and C-UKF formulations. Furthermore, the performance of the proposed C-EnKF scheme was found to be satisfactory when employed for state estimation in a system having constraints on process noise.</li>
</ul>

<h4>Key Takeaways from Constrained nonlinear state estimation based on the UKF approach [3]:</h4>

<ul>
  <li>Overview of several UKF based nonlinear estimation algorithms as an alternative to the EKF.</li>
  <li>Suggested a reformulation of the correction step which can be applied to all the presented UKF algorithms, presented a QP formulation of the NLP UKF (which also can be applied to all of the presented UKF algorithms).</li>
  <li>Proposed alternatives to realize constraints within the UKF approach.</li>
 </ul>
 <h3>Mathematical Formualtion </h3>
  <h4>Bayes Filter</h4>

  <p>The Kalman Filter is based on the Bayes theorem and Markov Assumption. From the Bayes theorem we get the following equation:</p>
  <img src="Pictures/pic2.jpg" alt="Custom Image" width="300px" />

  <p>The above equation shows the probability of event A<sub>1</sub> occurring when the event B has occurred. The above result may then be extended to multiple events, whose detailed derivation has been given in Appendix-1.</p>

  <p>On the other hand, the Markov Assumption may be understood using Figure:</p>

  <p><img src="Pictures/pic3.jpg" alt="Markov Assumption Figure" style="width: 300px;"></p>

  <p>We see that at time <i>t-1</i> when we give input U, then we get state X at <i>t-1</i> and its measurement Z at time <i>t-1</i>. Similarly, at time <i>t</i>, we give input and obtain the state X at time <i>t</i>, whose measurement is Z<sub>t</sub>.
  </p>
  <p>Thus on observing the pattern we see that state X at time t depends upon state X at time t-1 and input U at time t while the measurement at time t depends on the state X at time t only .Mathematically it may be represented as : </p>
   <img src="Pictures/pic4.jpg" alt="Custom Image" width="270px" />

   <p>The final formulation of the Bayes filter is obtained by the combination of the Bayes theorem and Markov's assumption which is described in detail in Appendix-1.  
   </p>
  <img src="Pictures/pic5.jpg" alt="Custom Image" width="400px" />
  <p> From this we observe that  Posterior of State = Likelihood of state * (Previous Estimation)

  Kalman Filter is for linear systems where - the state X and the measurement Z can be represented linearly as-
  ( w in Z denotes the error in measurement)
</p><img src="Pictures/pic6.jpg" alt="Custom Image" width="250px" />
 
  <h4>Kalman  Filter</h4>
  <p>The Kalman Filter mathematical derivation is discussed in detail in Appendix-2. The basic algorithm for Kalman Filter can be represnted as :-</p>

  <img
        src="https://ars.els-cdn.com/content/image/1-s2.0-S0019057822004050-gr2.jpg"
        alt="Algorithm of Kalman Filter "
      />
  <sup>[6]</sup>
  <h4>Unscented Kalman  Filter</h4>
  <p>The Unscented Kalman Filter (UKF) is a variant of the Kalman filter that allows for nonlinear systems to be estimated. Here is the mathematical formulation of the UKF:
Let us assume we have a system described by the following state equation:
</p><img src="Pictures/pic7.jpg" alt="Custom Image" width="220px" />
 <p>where x <sub>k</sub> is the state at time k , f is the nonlinear state transition function, u <sub>k</sub> is the control input at time k, and w <sub>k-1</sub> is the process noise at time k-1.

 We also have measurements that are related to the state through the following observation equation:

</p>
<img src="Pictures/pic8.jpg" alt="Custom Image" width="150px" />
<p>where z <sub>k</sub> is the measurement at time k, h is the nonlinear observation function, v <sub>k</sub> and  is the measurement noise at time k.
  The UKF estimates the state of the system by maintaining a probability distribution over the possible states. Specifically, the UKF maintains a Gaussian distribution over the state at each time step, with mean x <sub>k</sub>  and covariance P <sub>k</sub> . The UKF works by propagating the mean and covariance of the state distribution through the nonlinear state transition function f and the nonlinear observation function h using a set of carefully chosen sigma points. These sigma points are chosen to capture the mean and covariance of the distribution, and to propagate them through the nonlinear functions in a way that preserves their moments.

  The propagation of the mean and covariance through the nonlinear functions is done in two steps: the prediction step and the update step.

  </p>
  <h4>Recursive Algorithm for UKF implementation </h4>
<ol>
  <li>Given x and P<sub>t-1</sub>, sample sigma points are found by computing eigenvalues and eigenvectors of P<sub>t-1</sub>.</li>
  
  <li>Propagate the sigma points through the nonlinear model to obtain <img src="Pictures/pic9.jpg" alt="Custom Image" width="120px" /></li>
  
  <li>From the (2n+1) sigma points, compute the mean and variance.<img src="Pictures/pic10.jpg" alt="Custom Image" width="700px" /></li>
  
  <li>Sample again (2n+1) sigma points for P<sub>t | t-1</sub>, sample.</li>
  
  <li>Transform the propagated sigma points to output estimate based on the nonlinear measurement equation, and compute the estimated output.</li>
  <img src="Pictures/pic12.jpg" alt="Custom Image" width="300px" />
  
  <li>Evaluate the innovation covariance and the cross-covariance by using (2n +1) points of propagated output estimates to find the Kalman gain.</li>
  <img src="Pictures/pic11.jpg" alt="Custom Image" width="800px" />
  <li>Update the state estimate with the Kalman gain.</li>
  <img src="Pictures/pic13.jpg" alt="Custom Image" width="230px" />
  <li>Update the a posteriori covariance.</li>
  <img src="Pictures/pic14.jpg" alt="Custom Image" width="170px" />
</ol>
<h3>Results and Discussion
</h3>
<h3>References</h3>
 
  <ol>
    <li>
      Wikipedia contributors, “Kalman filter,” Wikipedia, Mar. 18, 2024. <a href="https://en.wikipedia.org/wiki/Kalman_filter">(https://en.wikipedia.org/wiki/Kalman_filter))</a>
    </li>
    <li>
    J. Prakash, S. C. Patwardhan, and S. L. Shah, “Constrained nonlinear state estimation using Ensemble Kalman filters,” Industrial & Engineering Chemistry Research, vol. 49, no. 5, pp. 2242–2253, Feb. 2010, doi: 10.1021/ie900197s. 
    </li>
    <li>S. Kolås, B. A. Foss, and T. S. Schei, “Constrained nonlinear state estimation based on the UKF approach,” Computers & Chemical Engineering, vol. 33, no. 8, pp. 1386–1401, Aug. 2009, doi: 10.1016/j.compchemeng.2009.01.012.</li>
    <li>Rlabbe, “GitHub - rlabbe/Kalman-and-Bayesian-Filters-in-Python: Kalman Filter book using Jupyter Notebook. Focuses on building intuition and experience, not formal proofs.  Includes Kalman filters,extended Kalman filters, unscented Kalman filters, particle filters, and more. All exercises include solutions.,” GitHub. 
    <a href="https://github.com/rlabbeKalman-and-Bayesian-Filters-in-Python">(https://github.com/rlabbeKalman-and-Bayesian-Filters-in-Python))</a>
    </li>
    <li>
      Massachusetts Institute of Technology d’Arbeloff Laboratory and H. Asada, “MIT d’Arbeloff Laboratory,” MIT D’Arbeloff Lab, Mar. 04, 2021. <a href="https://darbelofflab.mit.edu/">(https://darbelofflab.mit.edu/)</a> 
    </li>
    <li>Z. Zhang, J. Jiang, J. Wu, and X. Zhu, “Efficient and optimal penetration path planning for stealth unmanned aerial vehicle using minimal radar cross-section tactics and modified A-Star algorithm,” ISA Transactions, vol. 134, pp. 42–57, Mar. 2023, doi: 10.1016/j.isatra.2022.07.032.</li>
  </ol>
</body>

