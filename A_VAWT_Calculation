% Parameters
L_x = 100000;     % domain length in x
L_z = 800;     % domain length in z
x_0 = L_x/4;   % Gaussian center x
z_0 = 150;     % Gaussian center z
A_HAWT = 0.5;       % forcing amplitude
U0 = 20;       % background velocity
sig_x = 50;    % Gaussian width x
sig_z = 40;    % Gaussian width z
N_x = 1280;     % number of x points (FFT-friendly)
N_z = 100;     % number of z intervals
delta = 0.01;

% Grids
x = linspace(0,L_x,N_x);      % x-grid
z = linspace(0,L_z,N_z+1);    % z-grid

[X,Z] = meshgrid(x,z); % Gridpoints



f_HAWT = -A_HAWT .* exp(-(X-x_0).^2/(2*sig_x^2)) .* exp(-(Z-z_0).^2/(2*sig_z^2));
bottom = 125;
top = 175;
f_VAWT = -A_HAWT .* exp(-(X-x_0).^2/(2*sig_x^2)) .* (tanh((Z-bottom)/delta) - tanh((Z-top)/delta));


%Calculate double integrals of f across full area domain using trapz
integral_f_HAWT = trapz(z, trapz(x, f_HAWT, 2)); 
integral_f_VAWT = trapz(z, trapz(x, f_VAWT, 2));

% Display the results of the integrals
fprintf('Integral of f_HAWT: %.4f\n', integral_f_HAWT);
fprintf('Integral of f_VAWT: %.4f\n', integral_f_VAWT);

A_VAWT = A_HAWT * ((integral_f_HAWT) / (integral_f_VAWT));

% Calculate the adjusted amplitude for the vertical axis wind turbine
fprintf('Adjusted amplitude for VAWT: %.8f\n', A_VAWT);
